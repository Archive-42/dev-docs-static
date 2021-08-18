Migrating from webkitAudioContext
=================================

The Web Audio API went through many iterations before reaching its current state. It was first implemented in WebKit, and some of its older parts were not immediately removed as they were replaced in the specification, leading to many sites using non-compatible code. In this article, we cover the differences in Web Audio API since it was first implemented in WebKit and how to update your code to use the modern Web Audio API.

The Web Audio standard was first implemented in [WebKit](https://webkit.org/), and the implementation was built in parallel with the work on the [specification](https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html) of the API. As the specification evolved and changes were made to the spec, some of the old implementation pieces were not removed from the WebKit (and Blink) implementations due to backwards compatibility reasons.

New engines implementing the Web Audio spec (such as Gecko) will only implement the official, final version of the specification, which means that code using `webkitAudioContext` or old naming conventions in the Web Audio specification may not immediately work out of the box in a compliant Web Audio implementation. This article attempts to summarize the areas where developers are likely to encounter these problems and provide examples on how to port such code to standards based [`AudioContext`](../audiocontext), which will work across different browser engines.

**Note**: There is a library called [webkitAudioContext monkeypatch](https://github.com/cwilso/webkitAudioContext-MonkeyPatch), which automatically fixes some of these changes to make most code targeting `webkitAudioContext` to work on the standards based `AudioContext` out of the box, but it currently doesn't handle all of the cases below. Please consult the [README file](https://github.com/cwilso/webkitAudioContext-MonkeyPatch/blob/gh-pages/README.md) for that library to see a list of APIs that are automatically handled by it.

Changes to the creator methods
------------------------------

Three of the creator methods on `webkitAudioContext` have been renamed in [`AudioContext`](../audiocontext).

-   `createGainNode()` has been renamed to <span class="page-not-created">`createGain`</span>.
-   `createDelayNode()` has been renamed to <span class="page-not-created">`createDelay`</span>.
-   `createJavaScriptNode()` has been renamed to <span class="page-not-created">`createScriptProcessor`</span>.

These are simple renames that were made in order to improve the consistency of these method names on [`AudioContext`](../audiocontext). If your code uses either of these names, like in the example below :

    // Old method names
    var gain = context.createGainNode();
    var delay = context.createDelayNode();
    var js = context.createJavascriptNode(1024);

you can rename the methods to look like this:

    // New method names
    var gain = context.createGain();
    var delay = context.createDelay();
    var js = context.createScriptProcessor(1024);

The semantics of these methods remain the same in the renamed versions.

Changes to starting and stopping nodes
--------------------------------------

In `webkitAudioContext`, there are two ways to start and stop [`AudioBufferSourceNode`](../audiobuffersourcenode) and [`OscillatorNode`](../oscillatornode): the `noteOn()` and `noteOff()` methods, and the `start()` and `stop()` methods. (<span class="page-not-created">`AudioBufferSourceNode `</span>has yet another way of starting output: the `noteGrainOn()` method.) The `noteOn()`/`noteGrainOn()`/`noteOff()` methods were the original way to start/stop output in these nodes, and in the newer versions of the specification, the `noteOn()` and `noteGrainOn()` methods were consolidated into a single `start()` method, and the `noteOff()` method was renamed to the `stop()` method.

In order to port your code, you can just rename the method that you're using. For example, if you have code like the below:

    var osc = context.createOscillator();
    osc.noteOn(1);
    osc.noteOff(1.5);

    var src = context.createBufferSource();
    src.noteGrainOn(1, 0.25);
    src.noteOff(2);

you can change it like this in order to port it to the standard AudioContext API:

    var osc = context.createOscillator();
    osc.start(1);
    osc.stop(1.5);

    var src = context.createBufferSource();
    src.start(1, 0.25);
    src.stop(2);

Remove synchronous buffer creation
----------------------------------

In the old WebKit implementation of Web Audio, there were two versions of `createBuffer()`, one which created an initially empty buffer, and one which took an existing [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing encoded audio, decoded it and returned the result in the form of an [`AudioBuffer`](../audiobuffer). The latter version of `createBuffer()` was potentially expensive, because it had to decode the audio buffer synchronously, and with the buffer being arbitrarily large, it could take a lot of time for this method to complete its work, and no other part of your web page's code could execute in the mean time.

Because of these problems, this version of the `createBuffer()` method has been removed, and you should use the asynchronous `decodeAudioData()` method instead.

The example below shows old code which downloads an audio file over the network, and then decoded it using `createBuffer()`:

    var xhr = new XMLHttpRequest();
    xhr.open("GET", "/path/to/audio.ogg", true);
    xhr.responseType = "arraybuffer";
    xhr.send();
    xhr.onload = function() {
      var decodedBuffer = context.createBuffer(xhr.response, false);
      if (decodedBuffer) {
        // Decoding was successful, do something useful with the audio buffer
      } else {
        alert("Decoding the audio buffer failed");
      }
    };

Converting this code to use `decodeAudioData()` is relatively simple, as can be seen below:

    var xhr = new XMLHttpRequest();
    xhr.open("GET", "/path/to/audio.ogg", true);
    xhr.responseType = "arraybuffer";
    xhr.send();
    xhr.onload = function() {
      context.decodeAudioData(xhr.response, function onSuccess(decodedBuffer) {
        // Decoding was successful, do something useful with the audio buffer
      }, function onFailure() {
        alert("Decoding the audio buffer failed");
      });
    };

Note that the `decodeAudioData()` method is asynchronous, which means that it will return immediately, and then when the decoding finishes, one of the success or failure callback functions will get called depending on whether the audio decoding was successful. This means that you may need to restructure your code to run the part which happened after the `createBuffer()` call in the success callback, as you can see in the example above.

Renaming of AudioParam.setTargetValueAtTime
-------------------------------------------

The `setTargetValueAtTime()` method on the [`AudioParam`](../audioparam) interface has been renamed to `setTargetAtTime()`. This is also a simple rename to improve the understandability of the API, and the semantics of the method are the same. If your code is using `setTargetValueAtTime()`, you can rename it to use `setTargetAtTime()`. For example, if we have code that looks like this:

      var gainNode = context.createGain();
      gainNode.gain.setTargetValueAtTime(0.0, 10.0, 1.0);

you can rename the method, and be compliant with the standard, like so:

      var gainNode = context.createGain();
      gainNode.gain.setTargetAtTime(0.0, 10.0, 1.0);

Enumerated values that changed
------------------------------

The original `webkitAudioContext` API used C-style number based enumerated values in the API. Those values have since been changed to use the Web IDL based enumerated values, which should be familiar because they are similar to things like the [`HTMLInputElement`](../htmlinputelement) property <span class="page-not-created">`type`</span>.

### OscillatorNode.type

[`OscillatorNode`](../oscillatornode)'s type property has been changed to use Web IDL enums. Old code using `webkitAudioContext` can be ported to standards based [`AudioContext`](../audiocontext) like below:

    // Old webkitAudioContext code:
    var osc = context.createOscillator();
    osc.type = osc.SINE;     // sine waveform
    osc.type = osc.SQUARE;   // square waveform
    osc.type = osc.SAWTOOTH; // sawtooth waveform
    osc.type = osc.TRIANGLE; // triangle waveform
    osc.setWaveTable(table);
    var isCustom = (osc.type == osc.CUSTOM); // isCustom will be true

    // New standard AudioContext code:
    var osc = context.createOscillator();
    osc.type = "sine";       // sine waveform
    osc.type = "square";     // square waveform
    osc.type = "sawtooth";   // sawtooth waveform
    osc.type = "triangle";   // triangle waveform
    osc.setPeriodicWave(table);  // Note: setWaveTable has been renamed to setPeriodicWave!
    var isCustom = (osc.type == "custom"); // isCustom will be true

### BiquadFilterNode.type

[`BiquadFilterNode`](../biquadfilternode)'s type property has been changed to use Web IDL enums. Old code using `webkitAudioContext` can be ported to standards based [`AudioContext`](../audiocontext) like below:

    // Old webkitAudioContext code:
    var filter = context.createBiquadFilter();
    filter.type = filter.LOWPASS;   // lowpass filter
    filter.type = filter.HIGHPASS;  // highpass filter
    filter.type = filter.BANDPASS;  // bandpass filter
    filter.type = filter.LOWSHELF;  // lowshelf filter
    filter.type = filter.HIGHSHELF; // highshelf filter
    filter.type = filter.PEAKING;   // peaking filter
    filter.type = filter.NOTCH;     // notch filter
    filter.type = filter.ALLPASS;   // allpass filter

    // New standard AudioContext code:
    var filter = context.createBiquadFilter();
    filter.type = "lowpass";        // lowpass filter
    filter.type = "highpass";       // highpass filter
    filter.type = "bandpass";       // bandpass filter
    filter.type = "lowshelf";       // lowshelf filter
    filter.type = "highshelf";      // highshelf filter
    filter.type = "peaking";        // peaking filter
    filter.type = "notch";          // notch filter
    filter.type = "allpass";        // allpass filter

### PannerNode.panningModel

[`PannerNode`](../pannernode)'s panningModel property has been changed to use Web IDL enums. Old code using `webkitAudioContext` can be ported to standards based [`AudioContext`](../audiocontext) like below:

    // Old webkitAudioContext code:
    var panner = context.createPanner();
    panner.panningModel = panner.EQUALPOWER;  // equalpower panning
    panner.panningModel = panner.HRTF;        // HRTF panning

    // New standard AudioContext code:
    var panner = context.createPanner();
    panner.panningModel = "equalpower";       // equalpower panning
    panner.panningModel = "HRTF";             // HRTF panning

### PannerNode.distanceModel

[`PannerNode`](../pannernode)'s `distanceModel` property has been changed to use Web IDL enums. Old code using `webkitAudioContext` can be ported to standards based [`AudioContext`](../audiocontext) like below:

    // Old webkitAudioContext code:
    var panner = context.createPanner();
    panner.distanceModel = panner.LINEAR_DISTANCE;      // linear distance model
    panner.distanceModel = panner.INVERSE_DISTANCE;     // inverse distance model
    panner.distanceModel = panner.EXPONENTIAL_DISTANCE; // exponential distance model

    // Mew standard AudioContext code:
    var panner = context.createPanner();
    panner.distanceModel = "linear";                    // linear distance model
    panner.distanceModel = "inverse";                   // inverse distance model
    panner.distanceModel = "exponential";               // exponential distance model

Gain control moved to its own node type
---------------------------------------

The Web Audio standard now controls all gain using the [`GainNode`](../gainnode). Instead of setting a `gain` property directly on an audio source, you connect the source to a gain node and then control the gain using that node's `gain` parameter.

### AudioBufferSourceNode

The `gain` attribute of [`AudioBufferSourceNode`](../audiobuffersourcenode) has been removed. The same functionality can be achieved by connecting the [`AudioBufferSourceNode`](../audiobuffersourcenode) to a gain node. See the following example:

    // Old webkitAudioContext code:
    var src = context.createBufferSource();
    src.buffer = someBuffer;
    src.gain.value = 0.5;
    src.connect(context.destination);
    src.noteOn(0);

    // New standard AudioContext code:
    var src = context.createBufferSource();
    src.buffer = someBuffer;
    var gain = context.createGain();
    src.connect(gain);
    gain.gain.value = 0.5;
    gain.connect(context.destination);
    src.start(0);

### AudioBuffer

The `gain` attribute of [`AudioBuffer`](../audiobuffer) has been removed. The same functionality can be achieved by connecting the [`AudioBufferSourceNode`](../audiobuffersourcenode) that owns the buffer to a gain node. See the following example:

    // Old webkitAudioContext code:
    var src = context.createBufferSource();
    src.buffer = someBuffer;
    src.buffer.gain = 0.5;
    src.connect(context.destination);
    src.noteOn(0);

    // New standard AudioContext code:
    var src = context.createBufferSource();
    src.buffer = someBuffer;
    var gain = context.createGain();
    src.connect(gain);
    gain.gain.value = 0.5;
    gain.connect(context.destination);
    src.start(0);

Removal of AudioBufferSourceNode.looping
----------------------------------------

The `looping` attribute of [`AudioBufferSourceNode`](../audiobuffersourcenode) has been removed. This attribute was an alias of the `loop` attribute, so you can just use the `loop` attribute instead. Instead of having code like this:

    var source = context.createBufferSource();
    source.looping = true;

you can change it to respect the last version of the specification:

    var source = context.createBufferSource();
    source.loop = true;

Note, the `loopStart` and `loopEnd` attributes are not supported in `webkitAudioContext`.

Changes to determining playback state
-------------------------------------

The `playbackState` attribute of [`AudioBufferSourceNode`](../audiobuffersourcenode) and [`OscillatorNode`](../oscillatornode) has been removed. Depending on why you used this attribute, you can use the following techniques to get the same information:

-   If you need to compare this attribute to `UNSCHEDULED_STATE`, you can basically remember whether you've called `start()` on the node or not.
-   If you need to compare this attribute to `SCHEDULED_STATE`, you can basically remember whether you've called `start()` on the node or not. You can compare the value of [`AudioContext.currentTime`](../baseaudiocontext/currenttime) to the first argument passed to `start()` to know whether playback has started or not.
-   If you need to compare this attribute to `PLAYING_STATE`, you can compare the value of [`AudioContext.currentTime`](../baseaudiocontext/currenttime) to the first argument passed to `start()` to know whether playback has started or not.
-   If you need to know when playback of the node is finished (which is the most significant use case of `playbackState`), there is a new ended event which you can use to know when playback is finished. Please see this code example:

<!-- -->

    // Old webkitAudioContext code:
    var src = context.createBufferSource();
    // Some time later...
    var isFinished = (src.playbackState == src.FINISHED_STATE);

    // New AudioContext code:
    var src = context.createBufferSource();
    function endedHandler(event) {
      isFinished = true;
    }
    var isFinished = false;
    src.onended = endedHandler;

The exact same changes have been applied to both [`AudioBufferSourceNode`](../audiobuffersourcenode) and [`OscillatorNode`](../oscillatornode), so you can apply the same techniques to both kinds of nodes.

Removal of AudioContext.activeSourceCount
-----------------------------------------

The `activeSourceCount` attribute has been removed from [`AudioContext`](../audiocontext). If you need to count the number of playing source nodes, you can maintain the count by handling the ended event on the source nodes, as shown above.

Code using the `activeSourceCount` attribute of the [`AudioContext`](../audiocontext), like this snippet:

      var src0 = context.createBufferSource();
      var src1 = context.createBufferSource();
      // Set buffers and other parameters...
      src0.start(0);
      src1.start(0);
      // Some time later...
      console.log(context.activeSourceCount);

could be rewritten like that:

      // Array to track the playing source nodes:
      var sources = [];
      // When starting the source, put it at the end of the array,
      // and set a handler to make sure it gets removed when the
      // AudioBufferSourceNode reaches its end.
      // First argument is the AudioBufferSourceNode to start, other arguments are
      // the argument to the |start()| method of the AudioBufferSourceNode.
      function startSource() {
        var src = arguments[0];
        var startArgs = Array.prototype.slice.call(arguments, 1);
        src.onended = function() {
          sources.splice(sources.indexOf(src), 1);
        }
        sources.push(src);
        src.start.apply(src, startArgs);
      }
      function activeSources() {
        return sources.length;
      }
      var src0 = context.createBufferSource();
      var src0 = context.createBufferSource();
      // Set buffers and other parameters...
      startSource(src0, 0);
      startSource(src1, 0);
      // Some time later, query the number of sources...
      console.log(activeSources());

Renaming of WaveTable
---------------------

The <span class="page-not-created">`WaveTable`</span> interface has been renamed to [`PeriodicWave`](../periodicwave). Here is how you can port old code using `WaveTable` to the standard AudioContext API:

    // Old webkitAudioContext code:
    var osc = context.createOscillator();
    var table = context.createWaveTable(realArray, imaginaryArray);
    osc.setWaveTable(table);

    // New standard AudioContext code:
    var osc = context.createOscillator();
    var table = context.createPeriodicWave(realArray, imaginaryArray);
    osc.setPeriodicWave(table);

Removal of some of the AudioParam read-only attributes
------------------------------------------------------

The following read-only attributes have been removed from AudioParam: `name`, `units`, `minValue`, and `maxValue`. These used to be informational attributes. Here is some information on how you can get these values if you need them:

-   The `name` attribute is a string representing the name of the [`AudioParam`](../audioparam) object. For example, the name of [`GainNode.gain`](../gainnode/gain) is `"gain"`. You can track where the [`AudioParam`](../audioparam) object is coming from in your code if you need this information.
-   The `minValue` and `maxValue` attributes are read-only values representing the nominal range for the [`AudioParam`](../audioparam). For example, for [`GainNode`](../gainnode), these values are 0 and 1, respectively. Note that these bounds are not enforced by the engine, and are merely used for informational purposes. As an example, it's perfectly valid to set a gain value to 2, or even -1. In order to find out these nominal values, you can consult the [specification](https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html).
-   The `units` attribute as implemented in `webkitAudioContext` implementations is unused, and always returns 0. There is no reason why you should need this attribute.

Removal of MediaElementAudioSourceNode.mediaElement
---------------------------------------------------

The `mediaElement` attribute of [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode) has been removed. You can keep a reference to the media element used to create this node if you need to access it later.

Removal of MediaStreamAudioSourceNode.mediaStream
-------------------------------------------------

The `mediaStream` attribute of [`MediaStreamAudioSourceNode`](../mediastreamaudiosourcenode) has been removed. You can keep a reference to the media stream used to create this node if you need to access it later.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Migrating_from_webkitAudioContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Migrating_from_webkitAudioContext</a>

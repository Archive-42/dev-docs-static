ScriptProcessorNode
===================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `ScriptProcessorNode` interface allows the generation, processing, or analyzing of audio using JavaScript.

**Note**: As of the August 29 2014 Web Audio API spec publication, this feature has been marked as deprecated, and was replaced by [AudioWorklet](https://webaudio.github.io/web-audio-api/#audioworklet) (see [`AudioWorkletNode`](audioworkletnode)).

The `ScriptProcessorNode` interface is an [`AudioNode`](audionode) audio-processing module that is linked to two buffers, one containing the input audio data, one containing the processed output audio data. An event, implementing the [`AudioProcessingEvent`](audioprocessingevent) interface, is sent to the object each time the input buffer contains new data, and the event handler terminates when it has filled the output buffer with data.

<img src="data:image/png;base64,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" alt="The ScriptProcessorNode stores the input in a buffer, send the audioprocess event. The EventHandler takes the input buffer and fill the output buffer which is sent to the output by the ScriptProcessorNode." width="306" height="174" />

The size of the input and output buffer are defined at the creation time, when the [`BaseAudioContext.createScriptProcessor`](baseaudiocontext/createscriptprocessor) method is called (both are defined by [`BaseAudioContext.createScriptProcessor`](baseaudiocontext/createscriptprocessor)'s `bufferSize` parameter). The buffer size must be a power of 2 between `256` and `16384`, that is `256`, `512`, `1024`, `2048`, `4096`, `8192` or `16384`. Small numbers lower the *latency*, but large number may be necessary to avoid audio breakup and glitches.

If the buffer size is not defined, which is recommended, the browser will pick one that its heuristic deems appropriate.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code> (not used in the default count mode)</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

Properties
----------

*Inherits properties from its parent, [`AudioNode`](audionode)*.

 [`ScriptProcessorNode.bufferSize`](scriptprocessornode/buffersize) <span class="badge inline readonly">Read only </span>   
Returns an integer representing both the input and output buffer size. Its value can be a power of 2 value in the range `256`–`16384`.

Methods
-------

*No specific methods; inherits methods from its parent, [`AudioNode`](audionode)*.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface:

`audioprocess`  
Fired when an input buffer of a `ScriptProcessorNode` is ready to be processed.  
Also available via the `onaudioprocess` event handler property.

Examples
--------

The following example shows basic usage of a `ScriptProcessorNode` to take a track loaded via [`AudioContext.decodeAudioData()`](baseaudiocontext/decodeaudiodata), process it, adding a bit of white noise to each audio sample of the input track (buffer) and play it through the [`AudioDestinationNode`](audiodestinationnode). For each channel and each sample frame, the `scriptNode.onaudioprocess` function takes the associated `audioProcessingEvent` and uses it to loop through each channel of the input buffer, and each sample in each channel, and add a small amount of white noise, before setting that result to be the output sample in each case.

**Note**: For a full working example, see our [script-processor-node](https://mdn.github.io/webaudio-examples/script-processor-node/) github repo (also view the [source code](https://github.com/mdn/webaudio-examples/blob/master/script-processor-node/index.html).)

    var myScript = document.querySelector('script');
    var myPre = document.querySelector('pre');
    var playButton = document.querySelector('button');

    // Create AudioContext and buffer source
    var audioCtx = new AudioContext();
    source = audioCtx.createBufferSource();

    // Create a ScriptProcessorNode with a bufferSize of 4096 and a single input and output channel
    var scriptNode = audioCtx.createScriptProcessor(4096, 1, 1);
    console.log(scriptNode.bufferSize);

    // load in an audio track via XHR and decodeAudioData

    function getData() {
      request = new XMLHttpRequest();
      request.open('GET', 'viper.ogg', true);
      request.responseType = 'arraybuffer';
      request.onload = function() {
        var audioData = request.response;

        audioCtx.decodeAudioData(audioData, function(buffer) {
        myBuffer = buffer;
        source.buffer = myBuffer;
      },
        function(e){"Error with decoding audio data" + e.err});
      }
      request.send();
    }

    // Give the node a function to process audio events
    scriptNode.onaudioprocess = function(audioProcessingEvent) {
      // The input buffer is the song we loaded earlier
      var inputBuffer = audioProcessingEvent.inputBuffer;

      // The output buffer contains the samples that will be modified and played
      var outputBuffer = audioProcessingEvent.outputBuffer;

      // Loop through the output channels (in this case there is only one)
      for (var channel = 0; channel < outputBuffer.numberOfChannels; channel++) {
        var inputData = inputBuffer.getChannelData(channel);
        var outputData = outputBuffer.getChannelData(channel);

        // Loop through the 4096 samples
        for (var sample = 0; sample < inputBuffer.length; sample++) {
          // make output equal to the same as the input
          outputData[sample] = inputData[sample];

          // add noise to each output sample
          outputData[sample] += ((Math.random() * 2) - 1) * 0.2;
        }
      }
    }

    getData();

    // wire up play button
    playButton.onclick = function() {
      source.connect(scriptNode);
      scriptNode.connect(audioCtx.destination);
      source.start();
    }

    // When the buffer source stops playing, disconnect everything
    source.onended = function() {
      source.disconnect(scriptNode);
      scriptNode.disconnect(audioCtx.destination);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#the-scriptprocessornode-interface---deprecated">Web Audio API<br />
<span class="small">The definition of 'ScriptProcessorNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`ScriptProcessorNode`

14

12

25

No

15

6

≤37

Yes

25

14

6

Yes

`audioprocess_event`

14

12

25

No

15

6

≤37

Yes

25

14

6

Yes

`bufferSize`

14

12

25

No

15

6

≤37

Yes

25

14

6

Yes

`onaudioprocess`

14

12

25

No

15

6

≤37

Yes

25

14

6

Yes

See also
--------

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ScriptProcessorNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ScriptProcessorNode</a>

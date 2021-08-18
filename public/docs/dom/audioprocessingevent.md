# AudioProcessingEvent

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [Web Audio API](web_audio_api) `AudioProcessingEvent` represents events that occur when a [`ScriptProcessorNode`](scriptprocessornode) input buffer is ready to be processed.

**Note**: As of the August 29 2014 Web Audio API spec publication, this feature has been marked as deprecated, and is soon to be replaced by [AudioWorklet](https://webaudio.github.io/web-audio-api/#audioworklet).

## Properties

_The list below includes the properties inherited from its parent, [`Event`](event)_.

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Property</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>target</code> <span class="badge inline readonly">Read only </span></td><td><a href="eventtarget"><code>EventTarget</code></a></td><td>The event target (the topmost target in the DOM tree).</td></tr><tr class="even"><td><code>type</code> <span class="badge inline readonly">Read only </span></td><td><a href="domstring"><code>DOMString</code></a></td><td>The type of event.</td></tr><tr class="odd"><td><code>bubbles</code> <span class="badge inline readonly">Read only </span></td><td><code>boolean</code></td><td>Does the event normally bubble?</td></tr><tr class="even"><td><code>cancelable</code> <span class="badge inline readonly">Read only </span></td><td><code>boolean</code></td><td>Is it possible to cancel the event?</td></tr><tr class="odd"><td><code>playbackTime</code> <span class="badge inline readonly">Read only </span></td><td><code>double</code></td><td>The time when the audio will be played, as defined by the time of <a href="baseaudiocontext/currenttime"><code>AudioContext.currentTime</code></a></td></tr><tr class="even"><td><code>inputBuffer</code> <span class="badge inline readonly">Read only </span></td><td><a href="audiobuffer"><code>AudioBuffer</code></a></td><td>The buffer containing the input audio data to be processed. The number of channels is defined as a parameter, <code>numberOfInputChannels</code>, of the factory method <a href="baseaudiocontext/createscriptprocessor"><code>AudioContext.createScriptProcessor()</code></a>. Note the returned <code>AudioBuffer</code> is only valid in the scope of the <code>onaudioprocess</code> function.</td></tr><tr class="odd"><td><code>outputBuffer</code> <span class="badge inline readonly">Read only </span></td><td><a href="audiobuffer"><code>AudioBuffer</code></a></td><td><p>The buffer where the output audio data should be written. The number of channels is defined as a parameter, <code>numberOfOutputChannels</code>, of the factory method <a href="baseaudiocontext/createscriptprocessor"><code>AudioContext.createScriptProcessor()</code></a>. Note the returned <code>AudioBuffer</code> is only valid in the scope of the <code>onaudioprocess</code> function.</p></td></tr></tbody></table>

## Example

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

## Browser compatibility

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

`AudioProcessingEvent`

14

12

25

No

15

6

≤37

18

25

14

Yes

1.0

`AudioProcessingEvent`

57

79

No

No

44

14.1

57

57

No

43

14.5

7.0

`inputBuffer`

14

12

25

No

15

6

≤37

18

25

14

Yes

1.0

`outputBuffer`

14

12

25

No

15

6

≤37

18

25

14

Yes

1.0

`playbackTime`

14

12

25

No

15

6

≤37

18

25

14

Yes

1.0

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioProcessingEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioProcessingEvent</a>

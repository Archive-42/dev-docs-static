ScriptProcessorNode.onaudioprocess
==================================

Syntax
------

**Note**: As of the August 29 2014 Web Audio API spec publication, this feature has been marked as deprecated, and is soon to be replaced by [Audio Workers](../web_audio_api#audio_workers).

The `onaudioprocess` event handler of the [`ScriptProcessorNode`](../scriptprocessornode) interface represents the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) to be called for the `audioprocess` event that is dispatched to `ScriptProcessorNode` node types. An event of type [`AudioProcessingEvent`](../audioprocessingevent) will be dispatched to the event handler.

    var audioCtx = new AudioContext();
    var scriptNode = audioCtx.createScriptProcessor(4096, 1, 1);
    scriptNode.onaudioprocess = function() { ... }

Example
-------

The following example shows basic usage of a `ScriptProcessorNode` to take a track loaded via [`AudioContext.decodeAudioData()`](../baseaudiocontext/decodeaudiodata), process it, adding a bit of white noise to each audio sample of the input track (buffer) and play it through the [`AudioDestinationNode`](../audiodestinationnode). For each channel and each sample frame, the `scriptNode.onaudioprocess` function takes the associated `audioProcessingEvent` and uses it to loop through each channel of the input buffer, and each sample in each channel, and add a small amount of white noise, before setting that result to be the output sample in each case.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#widl-ScriptProcessorNode-onaudioprocess">Web Audio API<br />
<span class="small">The definition of 'onaudioprocess' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

-   [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ScriptProcessorNode/onaudioprocess" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ScriptProcessorNode/onaudioprocess</a>

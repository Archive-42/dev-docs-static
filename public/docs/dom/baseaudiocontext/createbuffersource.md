# BaseAudioContext.createBufferSource()

The `createBufferSource()` method of the [`BaseAudioContext`](../baseaudiocontext) Interface is used to create a new [`AudioBufferSourceNode`](../audiobuffersourcenode), which can be used to play audio data contained within an [`AudioBuffer`](../audiobuffer) object. [`AudioBuffer`](../audiobuffer)s are created using [`BaseAudioContext.createBuffer`](createbuffer) or returned by [`BaseAudioContext.decodeAudioData`](decodeaudiodata) when it successfully decodes an audio track.

## Syntax

    var source = baseAudioContext.createBufferSource();

### Returns

An [`AudioBufferSourceNode`](../audiobuffersourcenode).

## Example

In this example, we create a two second buffer, fill it with white noise, and then play it via an [`AudioBufferSourceNode`](../audiobuffersourcenode). The comments should clearly explain what is going on.

**Note**: You can also [run the code live](https://mdn.github.io/webaudio-examples/audio-buffer/), or [view the source](https://github.com/mdn/webaudio-examples/blob/master/audio-buffer/index.html).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var button = document.querySelector('button');
    var pre = document.querySelector('pre');
    var myScript = document.querySelector('script');

    pre.innerHTML = myScript.innerHTML;

    // Stereo
    var channels = 2;
    // Create an empty two second stereo buffer at the
    // sample rate of the AudioContext
    var frameCount = audioCtx.sampleRate * 2.0;

    var myArrayBuffer = audioCtx.createBuffer(channels, frameCount, audioCtx.sampleRate);

    button.onclick = function() {
      // Fill the buffer with white noise;
      //just random values between -1.0 and 1.0
      for (var channel = 0; channel < channels; channel++) {
       // This gives us the actual ArrayBuffer that contains the data
       var nowBuffering = myArrayBuffer.getChannelData(channel);
       for (var i = 0; i < frameCount; i++) {
         // Math.random() is in [0; 1.0]
         // audio needs to be in [-1.0; 1.0]
         nowBuffering[i] = Math.random() * 2 - 1;
       }
      }

      // Get an AudioBufferSourceNode.
      // This is the AudioNode to use when we want to play an AudioBuffer
      var source = audioCtx.createBufferSource();
      // set the buffer in the AudioBufferSourceNode
      source.buffer = myArrayBuffer;
      // connect the AudioBufferSourceNode to the
      // destination so we can hear the sound
      source.connect(audioCtx.destination);
      // start the source playing
      source.start();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createbuffersource">Web Audio API<br />
<span class="small">The definition of 'createBufferSource()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createBufferSource`

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

6

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createBufferSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createBufferSource</a>

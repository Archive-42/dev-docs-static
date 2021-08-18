# AudioBufferSourceNode.buffer

The `buffer` property of the [`AudioBufferSourceNode`](../audiobuffersourcenode) interface provides the ability to play back audio using an [`AudioBuffer`](../audiobuffer) as the source of the sound data.

If the `buffer` property is set to the value `null`, the node generates a single channel containing silence (that is, every sample is 0).

## Syntax

    AudioBufferSourceNode.buffer = soundBuffer;

### Value

An [`AudioBuffer`](../audiobuffer) which contains the data representing the sound which the node will play.

## Example

For a full working example, see [this code running live](https://mdn.github.io/webaudio-examples/audio-buffer/), or [view the source](https://github.com/mdn/webaudio-examples/blob/master/audio-buffer/index.html).

    var myArrayBuffer = audioCtx.createBuffer(2, frameCount, audioCtx.sampleRate);

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffersourcenode-buffer">Web Audio API<br />
<span class="small">The definition of 'buffer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`buffer`

14

12

25

Firefox currently handles the value `null` incorrectly. Instead of producing a node that generates a single channel of silence, the node becomes unusable and will be ignored if you attempt to connect it to anything.

No

15

6

≤37

18

25

Firefox currently handles the value `null` incorrectly. Instead of producing a node that generates a single channel of silence, the node becomes unusable and will be ignored if you attempt to connect it to anything.

14

6

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [Web Audio API](../web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/buffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/buffer</a>

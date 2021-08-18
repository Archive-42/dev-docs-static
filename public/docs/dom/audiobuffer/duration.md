# AudioBuffer.duration

The `duration` property of the [`AudioBuffer`](../audiobuffer) interface returns a double representing the duration, in seconds, of the PCM data stored in the buffer.

## Syntax

    var myArrayBuffer = audioCtx.createBuffer(2, frameCount, audioCtx.sampleRate);
    myArrayBuffer.duration;

### Value

A double.

## Example

    // Stereo
    var channels = 2;

    // Create an empty two second stereo buffer at the
    // sample rate of the AudioContext
    var frameCount = audioCtx.sampleRate * 2.0;
    var myArrayBuffer = audioCtx.createBuffer(2, frameCount, audioCtx.sampleRate);

    button.onclick = function() {
      // Fill the buffer with white noise;
      // just random values between -1.0 and 1.0
      for (var channel = 0; channel < channels; channel++) {
        // This gives us the actual ArrayBuffer that contains the data
        var nowBuffering = myArrayBuffer.getChannelData(channel);
        for (var i = 0; i < frameCount; i++) {
          // Math.random() is in [0; 1.0]
          // audio needs to be in [-1.0; 1.0]
          nowBuffering[i] = Math.random() * 2 - 1;
        }
      }

      console.log(myArrayBuffer.duration);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffer-duration">Web Audio API<br />
<span class="small">The definition of 'duration' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`duration`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer/duration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer/duration</a>

# BaseAudioContext.sampleRate

The `sampleRate` property of the [`BaseAudioContext`](../baseaudiocontext) interface returns a floating point number representing the sample rate, in samples per second, used by all nodes in this audio context. This limitation means that sample-rate converters are not supported.

## Syntax

    baseAudioContext.sampleRate;

### Value

A floating point number indicating the audio context's sample rate, in samples per second.

## Example

**Note**: for a full Web Audio example implementation, see one of our Web Audio Demos on the [MDN Github repo](https://github.com/mdn/), like [panner-node](https://github.com/mdn/panner-node). Try entering `audioCtx.sampleRate` into your browser console.

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();
    // Older webkit/blink browsers require a prefix

    ...

    console.log(audioCtx.sampleRate);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-samplerate">Web Audio API<br />
<span class="small">The definition of 'sampleRate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`sampleRate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/sampleRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/sampleRate</a>

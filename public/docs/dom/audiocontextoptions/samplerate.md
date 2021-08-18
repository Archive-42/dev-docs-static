# AudioContextOptions.sampleRate

The [`AudioContextOptions`](../audiocontextoptions) dictionary (used when instantiating an [`AudioContext`](../audiocontext)) may contain a property named `sampleRate`, which indicates the sample rate to use for the new context. The value must be a floating-point value indicating the sample rate, in samples per second, for which to configure the new context; additionally, the value must be one which is supported by [`AudioBuffer.sampleRate`](../audiobuffer/samplerate).

## Syntax

    audioContextOptions.sampleRate = 44100;

    var sampleRate = audioContextOptions.sampleRate;

### Value

The desired sample rate for the `AudioContext`, specified in samples per second. The value must be compatible with [`AudioBuffer.sampleRate`](../audiobuffer/samplerate). This value should typically be between 8,000 Hz and 96,000 Hz; the default will vary depending on the output device, but the sample rate 44,100 Hz is the most common.

If the `sampleRate` property is not included in the options, or the options are not specified when creating the audio context, the new context's output device's preferred sample rate is used by default.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontextoptions-samplerate">Web Audio API<br />
<span class="small">The definition of 'AudioContextOptions.sampleRate' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

74

79

61

No

No

No

74

74

61

?

No

11.0

## See also

- [`AudioContext`](../audiocontext): The interface describing an audio context
- [`AudioContext()`](../audiocontext/audiocontext): The audio context constructor, which accepts a [`AudioContextOptions`](../audiocontextoptions) object as an input.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContextOptions/sampleRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContextOptions/sampleRate</a>

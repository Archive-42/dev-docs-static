# AudioBufferSourceNode.AudioBufferSourceNode()

The `AudioBufferSourceNode()` constructor creates a new [`AudioBufferSourceNode`](../audiobuffersourcenode) object instance.

## Syntax

    var audioBufferSourceNode = new AudioBufferSourceNode(context, options)

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary_.

_context_  
A reference to an [`AudioContext`](../audiocontext).

_options_ <span class="badge inline optional">Optional</span>  
Options are as follows:

- `buffer`: An instance of [`AudioBuffer`](../audiobuffer) to be played.
- `detune`: A value in cents to modulate the speed of audio stream rendering. Its nominal range is (-∞ to +∞). The default is `0`.
- `loop`: A boolean indicating whether the audio should play in a loop. The default is `false`. If the loop is dynamically modified during playback, the new value will take effect on the next processing block of audio.
- `loopEnd`: An optional value, in seconds, where looping should end if the loop attribute is `true`. The default is `0`. Its value is exclusive to the content of the loop. The sample frames, comprising the loop, run from the values `loopStart` to `loopEnd`-(1/`sampleRate`). It's sensible to set this to a value between 0 and the duration of the buffer. If `loopEnd` is less than 0, looping will end at 0. If `loopEnd` is greater than the duration of the buffer, looping will end at the end of the buffer. This attribute is converted to an exact sample frame offset within the buffer, by multiplying by the buffer's sample rate and rounding to the nearest integer value. Thus, its behavior is independent of the value of the `playbackRate` parameter.

- `loopStart`: An optional value in seconds, where looping should begin if the loop attribute is `true`. The default is `0`. It's sensible to set this to a value between 0 and the duration of the buffer. If `loopStart` is less than 0, looping will begin at 0. If `loopStart` is greater than the duration of the buffer, looping will begin at the end of the buffer. This attribute is converted to an exact sample frame offset within the buffer, by multiplying by the buffer's sample rate and rounding to the nearest integer value. Thus, its behavior is independent of the value of the `playbackRate` parameter.
- `playbackRate`: The speed at which to render the audio stream. Its default value is `1`. This parameter is k-rate. This is a compound parameter with detune. Its nominal range is (-∞ to +∞).

### Return value

A new [`AudioBufferSourceNode`](../audiobuffersourcenode) object instance.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioBufferSourceNode">Web Audio API<br />
<span class="small">The definition of 'AudioBufferSourceNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AudioBufferSourceNode`

55

Before version 59, the default values were not supported.

79

53

No

42

14.1

55

Before version 59, the default values were not supported.

55

Before version 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/AudioBufferSourceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/AudioBufferSourceNode</a>

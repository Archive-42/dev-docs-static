# AudioContext.outputLatency

The `outputLatency` read-only property of the [`AudioContext`](../audiocontext) Interface provides an estimation of the output latency of the current audio context.

This is the time, in seconds, between the browser passing an audio buffer out of an audio graph over to the host system's audio subsystem to play, and the time at which the first sample in the buffer is actually processed by the audio output device.

It varies depending on the platform and the available hardware.

## Syntax

    var outputLatency = audioCtx.outputLatency;

### Value

A double representing the output latency in seconds.

## Example

    const audioCtx = new AudioContext();
    console.log(audioCtx.outputLatency);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-outputlatency">Web Audio API<br />
<span class="small">The definition of 'outputLatency' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`outputLatency`

No

No

70

No

No

No

No

No

No

No

No

No

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [Web Audio API](../web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/outputLatency" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/outputLatency</a>

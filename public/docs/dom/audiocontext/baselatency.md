# AudioContext.baseLatency

The `baseLatency` read-only property of the [`AudioContext`](../audiocontext) interface returns a double that represents the number of seconds of processing latency incurred by the `AudioContext` passing an audio buffer from the [`AudioDestinationNode`](../audiodestinationnode) — i.e. the end of the audio graph — into the host system's audio subsystem ready for playing.

**Note**: You can request a certain latency during [construction time](audiocontext) with the `latencyHint` option, but the browser may ignore the option.

## Syntax

    var baseLatency = audioCtx.baseLatency;

### Value

A double representing the base latency in seconds.

## Example

    // default latency ("interactive")
    const audioCtx1 = new AudioContext();
    console.log(audioCtx1.baseLatency); // 0.00

    // higher latency ("playback")
    const audioCtx2 = new AudioContext({ latencyHint: 'playback' });
    console.log(audioCtx2.baseLatency); // 0.15

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiocontext-baselatency">Web Audio API<br />
<span class="small">The definition of 'baseLatency' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`baseLatency`

58

79

70

No

45

14.1

58

58

No

43

14.5

7.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [Web Audio API](../web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/baseLatency" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/baseLatency</a>

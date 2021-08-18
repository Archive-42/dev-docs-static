# AudioWorklet

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `AudioWorklet` interface of the [Web Audio API](web_audio_api) is used to supply custom audio processing scripts that execute in a separate thread to provide very low latency audio processing. The worklet's code is run in the [`AudioWorkletGlobalScope`](audioworkletglobalscope) global execution context, using a separate Web Audio thread which is shared by the worklet and other audio nodes.

Access the audio context's instance of `AudioWorklet` through the [`BaseAudioContext.audioWorklet`](baseaudiocontext/audioworklet) property.

## Properties

_The `AudioWorklet` interface does not define any properties of its own, but does inherit properties of [`Worklet`](worklet)._

## Methods

_This interface inherits methods from [`Worklet`](worklet). The `AudioWorklet` interface does not define any methods of its own._

## Events

_`AudioWorklet` has no events to which it responds._

## Examples

See [`AudioWorkletNode`](audioworkletnode) for complete examples of custom audio node creation.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audioworklet">Web Audio API<br />
<span class="small">The definition of 'AudioWorklet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AudioWorklet`

66

79

76

No

Yes

14.1

66

66

79

Yes

14.5

9.0

## See also

- [`AudioWorkletGlobalScope`](audioworkletglobalscope) — the global execution context of an `AudioWorklet`
- [Web Audio API](web_audio_api)
- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioWorklet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioWorklet</a>

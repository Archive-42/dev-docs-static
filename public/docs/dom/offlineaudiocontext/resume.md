# OfflineAudioContext.resume()

The `resume()` method of the [`OfflineAudioContext`](../offlineaudiocontext) interface resumes the progression of time in an audio context that has been suspended. The promise resolves immediately because the `OfflineAudioContext` does not require the audio hardware. If the context is not currently suspended or the rendering has not started, the promise is rejected with [`InvalidStateError`](../domexception#exception-invalidstateerror).

## Syntax

    OfflineAudioContext.resume().then(function() { ... });

### Parameters

None.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolving to void.

### Exceptions

The promise is rejected when the following exception is encountered.

- [`InvalidStateError`](../domexception#exception-invalidstateerror) if the context is not currently suspended or the rendering has not started.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-offlineaudiocontext-resume">Web Audio API<br />
<span class="small">The definition of 'resume()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`resume`

49

≤18

No

No

36

No

49

49

No

36

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/resume" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/resume</a>

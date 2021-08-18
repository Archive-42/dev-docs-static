# OfflineAudioCompletionEvent.OfflineAudioCompletionEvent()

The `OfflineAudioCompletionEvent()` constructor of the [Web Audio API](../web_audio_api) creates a new [`OfflineAudioCompletionEvent`](../offlineaudiocompletionevent) object instance.

**Note**: You wouldn't generally use the constructor manually. `OfflineAudioCompletionEvent`s are despatched to [`OfflineAudioContext`](../offlineaudiocontext) instances for legacy reasons.

## Syntax

    var offlineAudioCompletionEvent = new OfflineAudioCompletionEvent(type, init)

### Parameters

_type_ <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) representing the type of object to create.

_init_ <span class="badge inline optional">Optional</span>  
Options are as follows:

- `renderedBuffer`: The rendered [`AudioBuffer`](../audiobuffer) containing the audio data.

### Return value

A new [`OfflineAudioCompletionEvent`](../offlineaudiocompletionevent) object instance.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-offlineaudiocompletionevent-offlineaudiocompletionevent">Web Audio API<br />
<span class="small">The definition of 'OfflineAudioCompletionEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`OfflineAudioCompletionEvent`

57

Before Chrome 59, the default values were not supported.

≤79

53

No

42

Yes

57

Before version 59, the default values were not supported.

57

Before Chrome 59, the default values were not supported.

53

42

Yes

6.0

Before Samsung Internet 7.0, the default values were not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioCompletionEvent/OfflineAudioCompletionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioCompletionEvent/OfflineAudioCompletionEvent</a>

# MediaRecorderErrorEvent()

The ` MediaRecorderErrorEvent``() ` constructor creates a new [`MediaRecorderErrorEvent`](../mediarecordererrorevent) object that represents an error that occurred during the recording of media by the [MediaStream Recording API](../mediastream_recording_api).

In general, you won't create these yourself; they are delivered to your implementation of [`MediaRecorder.onerror`](../mediarecorder/onerror) when errors occur while recording media.

## Syntax

    var errorEvent = new MediaRecorderErrorEvent(errorInfo)

### Parameters

`errorInfo`  
An object describing the error object to be created. It _must_ contain the `error` property at a minimum.

`error`  
A [`DOMException`](../domexception) that describes the error that occurred. This object's [`name`](../domexception/name) property should indicate the name of the error that occurred. The other fields may or may not be present.

Some [user agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) add to the `error` object other properties that provide information such as stack dumps, the name of the JavaScript file and the line number where the error occurred, and other debugging aids, but you should not rely on this information in a production environment.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#dom-mediarecordererrorevent-mediarecordererrorevent">MediaStream Recording<br />
<span class="small">The definition of 'MediaRecorderErrorEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaRecorderErrorEvent`

No

Uses a generic event with an `error` property.

No

Uses a generic event with an `error` property.

57

No

No

Uses a generic event with an `error` property.

14

No

No

Uses a generic event with an `error` property.

57

No

Uses a generic event with an `error` property.

14

No

Uses a generic event with an `error` property.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorderErrorEvent/MediaRecorderErrorEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorderErrorEvent/MediaRecorderErrorEvent</a>

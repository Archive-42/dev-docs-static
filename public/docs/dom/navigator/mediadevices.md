Navigator.mediaDevices
======================

The `Navigator.mediaDevices` read-only property returns a [`MediaDevices`](../mediadevices) object, which provides access to connected media input devices like cameras and microphones, as well as screen sharing.

Syntax
------

    var mediaDevices = navigator.mediaDevices;

### Return value

The [`MediaDevices`](../mediadevices) singleton object. Usually, you just use this object's members directly, such as by calling [`navigator.mediaDevices.getUserMedia()`](../mediadevices/getusermedia).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#mediadevices">Media Capture and Streams<br />
<span class="small">The definition of 'NavigatorUserMedia.mediaDevices' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`mediaDevices`

47

12

36

No

34

11

47

47

36

34

11

5.0

`secure_context_required`

74

79

69

No

No

No

74

74

No

No

No

11.0

See also
--------

-   [Media Capture and Streams API](../media_streams_api): The entry point to the documentation about the entire media stream API.
-   [WebRTC API](../webrtc_api): Documentation about the WebRTC API, which is closely related.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaDevices</a>

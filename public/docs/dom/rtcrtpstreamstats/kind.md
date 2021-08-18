RTCRtpStreamStats.kind
======================

The `kind` property of the [`RTCRtpStreamStats`](../rtcrtpstreamstats) dictionary is a string indicating whether the described [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) stream contains audio or video media. Its value is always either `"audio"` or `"video"`.

This property was previously called `mediaType`. The name was changed in the specification in February, 2018. See [Browser compatibility](#browser_compatibility) below to determine how this affects the browsers you're targeting.

Syntax
------

    mediaKind = RTCRtpStreamStats.kind;

### Value

A [`DOMString`](../domstring) whose value is `"audio"` if the track whose statistics are given by the `RTCRtpStreamStats` object contains audio, or `"video"` if the track contains video media.

This string will always be the same as the one provided by the associated [`MediaStreamTrack`](../mediastreamtrack) object's [`kind`](../mediastreamtrack/kind) property. It will also match the statistics object's <span class="page-not-created">`RTCCodecStats.codec`</span> property's media type.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcrtpstreamstats-kind">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCRtpStreamStats.kind' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`kind`

No

No

63

No

No

?

No

No

63

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/kind" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpStreamStats/kind</a>

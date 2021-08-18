# RTCIceCandidateStats.url

The [`RTCIceCandidateStats`](../rtcicecandidatestats) dictionary's `url` property specifies the URL of the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) server from which the described candidate was obtained. This property is _only_ available for local candidates.

## Syntax

    url = rtcIceCandidateStats.url;

### Value

A [`DOMString`](../domstring) specifying the URL of the ICE server from which the candidate described by the `RTCIceCandidateStats` was obtained. This is the same URL that would be received in the `icecandidate` event's <span class="page-not-created">`url`</span> property.

**Note:** This property does not exist for remote candidates.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcicecandidatestats-url">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'RTCIceCandidateStats.url' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`url`

No

No

No

No

?

?

No

No

No

?

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/url" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidateStats/url</a>

# RTCAnswerOptions

The `RTCAnswerOptions` dictionary is used to provide optional settings when creating an [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) answer using [`RTCPeerConnection.createOffer()`](rtcpeerconnection/createoffer) after receiving an offer from a remote peer. The `createOffer()` method's `options` parameter is of this type.

## Properties

_This dictionary inherits properties from the [`RTCOfferAnswerOptions`](rtcofferansweroptions) dictionary, on which it's based._

**Note:** At this time, `RTCAnswerOptions` does not have any additional properties defined beyond those included in [`RTCOfferAnswerOptions`](rtcofferansweroptions). However, this is likely to change in the future, so the type has been defined in preparation for that eventuality.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcansweroptions">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCAnswerOptions' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCAnswerOptions`

50

≤79

42

No

?

?

50

50

42

?

?

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCAnswerOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCAnswerOptions</a>

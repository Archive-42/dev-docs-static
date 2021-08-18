RTCOfferOptions
===============

The `RTCOfferOptions` dictionary is used to provide optional settings when creating an [`RTCPeerConnection`](rtcpeerconnection) offer with the [`createOffer()`](rtcpeerconnection/createoffer) method.

Properties
----------

*This dictionary also inherits properties from the [`RTCOfferAnswerOptions`](rtcofferansweroptions) dictionary, on which it's based.*

 [`iceRestart`](rtcofferoptions/icerestart) <span class="badge inline optional">Optional</span>   
A Boolean which, when set to `true`, tells `createOffer()` to generate and use new values for the identifying properties of the SDP it creates, resulting in a request that triggers renegotiation of the ICE connection. This is useful if network conditions have changed in a way that make the current configuration untenable or impractical, for instance.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcofferoptions">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCOfferOptions' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCOfferOptions`

50

≤79

42

`RTCOfferOptions` was not based on `RTCOfferAnswerOptions` until Firefox 42.

33

No

?

?

50

50

42

`RTCOfferOptions` was not based on `RTCOfferAnswerOptions` until Firefox 42.

33

?

?

5.0

`iceRestart`

50

≤79

48

No

?

?

50

50

48

?

?

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOfferOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOfferOptions</a>

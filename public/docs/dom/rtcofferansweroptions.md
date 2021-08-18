RTCOfferAnswerOptions
=====================

The [WebRTC API's](webrtc_api) `RTCOfferAnswerOptions` dictionary is used to specify options that configure and control the process of creating WebRTC offers or answers. It's used as the base type for the `options` parameter when calling [`createOffer()`](rtcpeerconnection/createoffer) or [`createAnswer()`](rtcpeerconnection/createanswer) on an [`RTCPeerConnection`](rtcpeerconnection).

Each of `createOffer()` and `createAnswer()` use `RTCOfferAnswerOptions` as the base type for their `options` parameter's dictionary. `createOffer()` uses [`RTCOfferOptions`](rtcofferoptions) and `createAnswer()` uses [`RTCAnswerOptions`](rtcansweroptions).

Properties
----------

 [`voiceActivityDetection`](rtcofferansweroptions/voiceactivitydetection) <span class="badge inline optional">Optional</span>   
For configurations of systems and codecs that are able to detect when the user is speaking and toggle muting on and off automatically, this option enables and disables that behavior. The default value is `true`, enabling this functionality

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcofferansweroptions">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCOfferAnswerOptions' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCOfferAnswerOptions`

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

`voiceActivityDetection`

50

≤79

No

No

?

?

50

50

No

?

?

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCOfferAnswerOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCOfferAnswerOptions</a>

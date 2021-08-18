RTCRtpSendParameters
====================

The WebRTC API's `RTCRtpSendParameters` dictionary is used to specify the parameters for an [`RTCRtpSender`](rtcrtpsender) when calling its [`setParameters()`](rtcrtpsender/setparameters) method.

Properties
----------

*In addition to the properties below, `RTCRtpSendParameters` inherits the properties from the [`RTCRtpParameters`](rtcrtpparameters) interface.*

[`encodings`](rtcrtpsendparameters/encodings)  
An array of [`RTCRtpEncodingParameters`](rtcrtpencodingparameters) objects, each specifying the parameters for a single codec that could be used to encode the track's media.

<span class="page-not-created">`transactionId`</span>  
A string containing a unique ID for the last set of parameters applied; this value is used to ensure that [`setParameters()`](rtcrtpsender/setparameters) can only be called to alter changes made by a specific previous call to [`getParameters()`](rtcrtpsender/getparameters). Once this parameter is initially set, it cannot be changed.

### Obsolete properties

 <span class="page-not-created">`degradationPreference`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Specifies the preferred way the WebRTC layer should handle optimizing bandwidth against quality in constrained-bandwidth situations; the value comes from the <span class="page-not-created">`RTCDegradationPreference`</span> enumerated string type, and the default is `balanced`.

 <span class="page-not-created">`priority`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A string from the <span class="page-not-created">`RTCPriorityType`</span> enumerated type which indicates the encoding's priority. The default value is `low`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsendparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSendParameters' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCRtpSendParameters`

69

≤79

No

Firefox expects an `RTCRtpParameters` object instead.

No

?

?

69

69

No

Firefox expects an `RTCRtpParameters` object instead.

?

?

10.0

`degradationPreference`

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

`encodings`

69

≤79

No

Firefox uses `RTCRtpParameters.encodings` instead.

No

?

?

69

69

No

Firefox uses `RTCRtpParameters.encodings` instead.

?

?

10.0

`priority`

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

`transactionId`

69

≤79

No

No

?

?

69

69

No

?

?

10.0

See also
--------

-   [`RTCRtpReceiveParameters`](rtcrtpreceiveparameters) and [`RTCRtpReceiver.getParameters()`](rtcrtpreceiver/getparameters)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSendParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSendParameters</a>

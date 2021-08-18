RTCIceParameters
================

The `RTCIceParameters` dictionary specifies the username fragment and password assigned to an [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) session. During ICE negotiation, each peer's username fragment and password are recorded in an `RTCIceParameters` object, which can be obtained from the [`RTCIceTransport`](rtcicetransport) by calling its [`getLocalParameters()`](rtcicetransport/getlocalparameters) or [`getRemoteParameters()`](rtcicetransport/getremoteparameters) method, depending on which end interests you.

Properties
----------

[`usernameFragment`](rtciceparameters/usernamefragment)  
A [`DOMString`](domstring) specifying the value of the ICE session's username fragment field, `ufrag`.

[`password`](rtciceparameters/password)  
A [`DOMString`](domstring) specifying the session's password string.

Usage notes
-----------

The username fragment and password uniquely identify the remote peer for the duration of the ICE session, and are used to both ensure security and to avoid crosstalk across multiple ongoing ICE sessions. See [`RTCIceCandidate.usernameFragment`](rtcicecandidate/usernamefragment) for further information.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtciceparameters">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceParameters' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCIceParameters`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceParameters" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceParameters</a>

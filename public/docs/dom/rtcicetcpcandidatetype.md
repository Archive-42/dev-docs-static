RTCIceTcpCandidateType
======================

The [WebRTC API's](webrtc_api) `RTCIceTcpCandidateType` enumerated type provides a set of [`DOMString`](domstring) values representing the types of TCP candidates.

Values
------

`"active"`  
The transport will try to open an outbound connection but won't receive inoming connection requests.

`"passive"`  
The transport will receive incoming connection requests but won't try to open an outbound connection.

`"so"`  
The transport will try to open a connection simultaneously with its peer.

Usage notes
-----------

The `RTCIceTcpCandidateType` type is used by the [`tcpType`](rtcicecandidate/tcptype) property of [`RTCIceCandidate`](rtcicecandidate) objects.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcicetcpcandidatetype">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTcpCandidateType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCIceTcpCandidateType`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTcpCandidateType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTcpCandidateType</a>

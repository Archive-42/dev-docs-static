RTCIceTransport.getLocalCandidates()
====================================

The **[`RTCIceTransport`](../rtcicetransport)** method `getLocalCandidates()` returns an array of [`RTCIceCandidate`](../rtcicecandidate) objects, one for each of the candidates that have been gathered by the local device during the current [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) agent session.

The local candidates are placed in this list by the ICE agent prior to being delivered to the local client's code in an `icecandidate` event so that the client can forward the candidates to the remote peer.

Syntax
------

    localCandidates = RTCIceTransport.getLocalCandidates();

### Parameters

None.

### Return value

A JavaScript [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) containing one [`RTCIceCandidate`](../rtcicecandidate) object for each candidate that has been identified so far during the ICE candidate gathering session.

You can't correlate these local candidates with matching remote candidates. To find the best match found so far, call [`RTCIceTransport.getSelectedCandidatePair()`](getselectedcandidatepair).

Example
-------

This simple example gets the local candidate list from the [`RTCIceTransport`](../rtcicetransport) for the first [`RTCRtpSender`](../rtcrtpsender) on the [`RTCPeerConnection`](../rtcpeerconnection), then outputs to the console all of the candidates in the list.

    var localCandidates = pc.getSenders()[0].transport.transport.getLocalCandidates();

    localCandidates.forEach(function(candidate, index)) {
      console.log("Candidate " + index + ": " + candidate.candidate);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport-getlocalcandidates">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.getLocalCandidates()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getLocalCandidates`

75

79

No

No

62

No

75

75

No

54

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getLocalCandidates" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getLocalCandidates</a>

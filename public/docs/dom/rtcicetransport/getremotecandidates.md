RTCIceTransport.getRemoteCandidates()
=====================================

The **[`RTCIceTransport`](../rtcicetransport)** method `getRemoteCandidates()` returns an array which contains one [`RTCIceCandidate`](../rtcicecandidate) for each of the candidates that have been received from the remote peer so far during the current [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) gathering session.

Each time your signaling code calls [`RTCPeerConnection.addIceCandidate()`](../rtcpeerconnection/addicecandidate) to add a received candidate to the ICE session, the ICE agent places it in the list returned by this function.

Syntax
------

    remoteCandidates = RTCIceTransport.getRemoteCandidates();

### Parameters

None.

### Return value

An array containing one [`RTCIceCandidate`](../rtcicecandidate) object for each candidate that has been received so far from the remote peer during the current ICE candidate gathering session.

It's important to keep in mind that there's no way to correlate these remote candidates with compatible local candidates. To find the best match found so far, call [`RTCIceTransport.getSelectedCandidatePair()`](getselectedcandidatepair).

Example
-------

This simple example gets the remote candidate list from the [`RTCIceTransport`](../rtcicetransport) for the first [`RTCRtpSender`](../rtcrtpsender) on the [`RTCPeerConnection`](../rtcpeerconnection), then outputs to the console all of the candidates in the list.

    var remoteCandidates = pc.getSenders()[0].transport.transport.getRemoteCandidates();

    remoteCandidates.forEach(function(candidate, index)) {
      console.log("Candidate " + index + ": " + candidate.candidate);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport-getremotecandidates">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.getRemoteCandidates()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getRemoteCandidates`

75

13

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getRemoteCandidates" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/getRemoteCandidates</a>

RTCPeerConnection.canTrickleIceCandidates
=========================================

The read-only **[`RTCPeerConnection`](../rtcpeerconnection)** property `canTrickleIceCandidates` returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which indicates whether or not the remote peer can accept [trickled ICE candidates](https://datatracker.ietf.org/doc/html/draft-ietf-mmusic-trickle-ice).

**ICE trickling** is the process of continuing to send candidates after the initial offer or answer has already been sent to the other peer.

This property is only set after having called [`RTCPeerConnection.setRemoteDescription()`](setremotedescription). Ideally, your signaling protocol provides a way to detect trickling support, so that you don't need to rely on this property. A WebRTC browser will always support trickle ICE. If trickling isn't supported, or you aren't able to tell, you can check for a falsy value for this property and then wait until the value of [`iceGatheringState`](icegatheringstate) changes to `"completed"` before creating and sending the initial offer. That way, the offer contains all of the candidates.

Syntax
------

     var canTrickle = RTCPeerConnection.canTrickleIceCandidates;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the remote peer can accept trickled ICE candidates and `false` if it cannot. If no remote peer has been established, this value is `null`.

**Note:** This property's value is determined once the local peer has called [`RTCPeerConnection.setRemoteDescription()`](setremotedescription); the provided description is used by the ICE agent to determine whether or not the remote peer supports trickled ICE candidates.

Example
-------

    const pc = new RTCPeerConnection();

    function waitToCompleteIceGathering(pc) {
        return new Promise(resolve => {
            pc.addEventListener('icegatheringstatechange', e => (e.target.iceGatheringState === 'complete') && resolve(pc.localDescription));
        });
    }

    // The following code might be used to handle an offer from a peer when
    // it isn't known whether it supports trickle ICE.
    async function newPeer(remoteOffer) {
        await pc.setRemoteDescription(remoteOffer);
        const offer = await pc.createOffer();
        await pc.setLocalDescription(offer);
        if (pc.canTrickleIceCandidates) return pc.localDescription;
        const answer = await waitToCompleteIceGathering(pc);
        sendAnswerToPeer(answer); //To peer via signaling channel
    }
    // Handle error with try/catch

    pc.addEventListener('icecandidate', e => (pc.canTrickleIceCandidates) && sendCandidateToPeer(e.candidate));

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-cantrickleicecandidates">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.canTrickleIceCandidates' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`canTrickleIceCandidates`

No

15-79

47

No

No

No

No

No

44

No

No

6.0

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCPeerConnection.addIceCandidate()`](addicecandidate)
-   [Lifetime of a WebRTC session](../webrtc_api/session_lifetime)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/canTrickleIceCandidates" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/canTrickleIceCandidates</a>

RTCPeerConnection.remoteDescription
===================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only property `RTCPeerConnection.remoteDescription` returns a [`RTCSessionDescription`](../rtcsessiondescription) describing the session (which includes configuration and media information) for the remote end of the connection. If this hasn't been set yet, this is `null`.

The returned value typically reflects a remote description which has been received over the signaling server (as either an offer or an answer) and then put into effect by your code calling [`RTCPeerConnection.setRemoteDescription()`](setremotedescription) in response.

Syntax
------

     var sessionDescription = peerConnection.remoteDescription;

On a more fundamental level, the returned value is the value of [`RTCPeerConnection.pendingRemoteDescription`](pendingremotedescription) if that property isn't `null`; otherwise, the value of [`RTCPeerConnection.currentRemoteDescription`](currentremotedescription) is returned. See [Pending and current descriptions](#) in [WebRTC connectivity](../webrtc_api/connectivity) for details on this algorithm and why it's used.

Example
-------

This example looks at the `remoteDescription` and displays an alert containing the [`RTCSessionDescription`](../rtcsessiondescription) object's `type` and `sdp` fields.

    var pc = new RTCPeerConnection();
    …
    var sd = pc.remoteDescription;
    if (sd) {
      alert("Remote session: type='" +
            sd.type + "'; sdp description='" +
            sd.sdp + "'");
    }
    else {
      alert("No remote session yet.");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-remotedescription">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.remoteDescription' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`remoteDescription`

24

15

22

No

43

Promise-based version and unprefixed.

38-43

Promise-based version.

11

≤37

Yes

44

43

Promise-based version and unprefixed.

41-43

Promise-based version.

11

6.0

See also
--------

-   [`RTCPeerConnection.setRemoteDescription()`](setremotedescription), [`RTCPeerConnection.pendingRemoteDescription`](pendingremotedescription), [`RTCPeerConnection.currentRemoteDescription`](currentremotedescription)
-   [`RTCPeerConnection.setLocalDescription()`](setlocaldescription), [`RTCPeerConnection.pendingLocalDescription`](pendinglocaldescription), [`RTCPeerConnection.currentLocalDescription`](currentlocaldescription), [`RTCPeerConnection.localDescription`](localdescription)
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/remoteDescription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/remoteDescription</a>

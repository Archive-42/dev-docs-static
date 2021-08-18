RTCPeerConnection.localDescription
==================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only property `RTCPeerConnection.localDescription` returns an [`RTCSessionDescription`](../rtcsessiondescription) describing the session for the local end of the connection. If it has not yet been set, this is `null`.

Syntax
------

     var sessionDescription = peerConnection.localDescription;

On a more fundamental level, the returned value is the value of [`RTCPeerConnection.pendingLocalDescription`](pendinglocaldescription) if that property isn't `null`; otherwise, the value of [`RTCPeerConnection.currentLocalDescription`](currentlocaldescription) is returned. See [Pending and current descriptions](#) in [WebRTC connectivity](../webrtc_api/connectivity) for details on this algorithm and why it's used.

Example
-------

This example looks at the `localDescription` and displays an alert containing the [`RTCSessionDescription`](../rtcsessiondescription) object's `type` and `sdp` fields.

    var pc = new RTCPeerConnection();
    …
    var sd = pc.localDescription;
    if (sd) {
      alert("Local session: type='" +
            sd.type + "'; sdp description='" +
            sd.sdp + "'");
    }
    else {
      alert("No local session yet.");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-localdescription">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.localDescription' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`localDescription`

24

15

22

No

43

Promise-based version.

37-43

11

≤37

25

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   [`RTCPeerConnection.setLocalDescription()`](setlocaldescription), [`RTCPeerConnection.pendingLocalDescription`](pendinglocaldescription), [`RTCPeerConnection.currentLocalDescription`](currentlocaldescription)
-   [`RTCPeerConnection.setRemoteDescription()`](setremotedescription), [`RTCPeerConnection.remoteDescription`](remotedescription), [`RTCPeerConnection.pendingRemoteDescription`](pendingremotedescription), [`RTCPeerConnection.currentRemoteDescription`](currentremotedescription)
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/localDescription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/localDescription</a>

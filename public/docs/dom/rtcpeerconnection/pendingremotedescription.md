RTCPeerConnection.pendingRemoteDescription
==========================================

The read-only property `RTCPeerConnection.pendingRemoteDescription` returns an [`RTCSessionDescription`](../rtcsessiondescription) object describing a pending configuration change for the remote end of the connection. This does not describe the connection as it currently stands, but as it may exist in the near future. Use [`RTCPeerConnection.currentRemoteDescription`](currentremotedescription) or [`RTCPeerConnection.remoteDescription`](remotedescription) to get the current session description for the remote endpoint. For details on the difference, see [Pending and current descriptions](#) in [WebRTC connectivity](../webrtc_api/connectivity).

Syntax
------

    sessionDescription = RTCPeerConnection.pendingRemoteDescription;

### Return value

If a remote description change is in progress, this is an [`RTCSessionDescription`](../rtcsessiondescription) describing the proposed configuration. Otherwise, this returns `null`.

Example
-------

This example looks at the `pendingRemoteDescription` to determine whether or not there's a description change being processed.

    var pc = new RTCPeerConnection();
    …
    var sd = pc.pendingRemoteDescription;
    if (sd) {
      // There's a description change underway!
    }
    else {
      // No description change pending
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-pendingremotedesc">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.pendingRemoteDescription' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`pendingRemoteDescription`

70

79

22

No

43

Promise-based version.

37-43

11

70

70

44

43

Promise-based version.

37-43

11

6.0

The addition of `pendingRemoteDescription` and [`currentRemoteDescription`](currentremotedescription) to the WebRTC spec is relatively recent. In browsers which don't support them, only [`remoteDescription`](remotedescription) is available.

See also
--------

-   [`RTCPeerConnection.setRemoteDescription()`](setremotedescription), [`RTCPeerConnection.currentRemoteDescription`](currentremotedescription), [`RTCPeerConnection.remoteDescription`](remotedescription)
-   [`RTCPeerConnection.setLocalDescription()`](setlocaldescription), [`RTCPeerConnection.localDescription`](localdescription), [`RTCPeerConnection.pendingLocalDescription`](pendinglocaldescription), [`RTCPeerConnection.currentLocalDescription`](currentlocaldescription)
-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/pendingRemoteDescription" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/pendingRemoteDescription</a>

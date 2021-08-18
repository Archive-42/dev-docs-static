RTCPeerConnection.removeTrack()
===============================

The `RTCPeerConnection.removeTrack()` method tells the local end of the connection to stop sending media from the specified track, without actually removing the corresponding [`RTCRtpSender`](../rtcrtpsender) from the list of senders as reported by [`RTCPeerConnection.getSenders()`](getsenders). If the track is already stopped, or is not in the connection's senders list, this method has no effect.

If the connection has already been negotiated ([`signalingState`](signalingstate) is set to `"stable"`), it is marked as needing to be negotiated again; the remote peer won't experience the change until this negotiation occurs. A `negotiationneeded` event is sent to the [`RTCPeerConnection`](../rtcpeerconnection) to let the local end know this negotiation must occur.

Syntax
------

    pc.removeTrack(sender);

### Parameters

`mediaTrack`  
A [`RTCRtpSender`](../rtcrtpsender) specifying the sender to remove from the connection.

### Return value

`undefined`.

### Exceptions

`InvalidStateError`  
The connection is not open.

Example
-------

This example adds a video track to a connection and sets up a listener on a close button which removes the track when the user clicks the button.

    var pc, sender;
    navigator.getUserMedia({video: true}, function(stream) {
      pc = new RTCPeerConnection();
      var track = stream.getVideoTracks()[0];
      sender = pc.addTrack(track, stream);
    });

    document.getElementById("closeButton").addEventListener("click", function(event) {
      pc.removeTrack(sender);
      pc.close();
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-removetrack">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.removeTrack()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`removeTrack`

64

79

22

No

51

11

64

64

44

47

11

6.0

See also
--------

-   [WebRTC API](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/removeTrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/removeTrack</a>

RTCPeerConnection.addStream()
=============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The *obsolete* [`RTCPeerConnection`](../rtcpeerconnection) method `addStream()` adds a [`MediaStream`](../mediastream) as a local source of audio or video. Instead of using this obsolete method, you should instead use [`addTrack()`](addtrack) once for each track you wish to send to the remote peer.

If the [`signalingState`](signalingstate) is set to `closed`, an `InvalidStateError` is raised. If the [`signalingState`](signalingstate) is set to `stable`, the event `negotiationneeded` is sent on the [`RTCPeerConnection`](../rtcpeerconnection) to indicate that [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) negotiation must be repeated to consider the new stream.

Syntax
------

    rtcPeerConnection.addStream(mediaStream);

### Parameters

`mediaStream`  
A [`MediaStream`](../mediastream) object indicating the stream to add to the WebRTC peer connection.

### Return value

None.

Example
-------

This simple example adds the audio and video stream coming from the user's camera to the connection.

    navigator.mediaDevices.getUserMedia({video:true, audio:true}, function(stream) {
      var pc = new RTCPeerConnection();
      pc.addStream(stream);
    });

Migrating to addTrack()
-----------------------

[Compatibility allowing](#browser_compatibility), you should update your code to instead use the [`addTrack()`](addtrack) method:

    navigator.getUserMedia({video:true, audio:true}, function(stream) {
      var pc = new RTCPeerConnection();
      stream.getTracks().forEach(function(track) {
        pc.addTrack(track, stream);
      });
    });

The newer [`addTrack()`](addtrack) API avoids confusion over whether later changes to the track-makeup of a stream affects a peer connection (they do not).

The exception is in Chrome, where `addStream()` *does* make the peer connection sensitive to later stream changes (though such changes do not fire the `negotiationneeded` event). If you are relying on the Chrome behavior, note that other browsers do not have it. You can write web compatible code using feature detection instead:

    // Add a track to a stream and the peer connection said stream was added to:

    stream.addTrack(track);
    if (pc.addTrack) {
      pc.addTrack(track, stream);
    } else {
      // If you have code listening for negotiationneeded events:
      setTimeout(() => pc.dispatchEvent(new Event('negotiationneeded')));
    }

    // Remove a track from a stream and the peer connection said stream was added to:

    stream.removeTrack(track);
    if (pc.removeTrack) {
      pc.removeTrack(pc.getSenders().find(sender => sender.track == track));
    } else {
      // If you have code listening for negotiationneeded events:
      setTimeout(() => pc.dispatchEvent(new Event('negotiationneeded')));
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#legacy-interface-extensions">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.addStream()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`addStream`

24

15

22

No

43

Promise-based version.

37-43

11-12

≤37

Yes

44

43

Promise-based version.

37-43

11-12

6.0

See also
--------

-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addStream</a>

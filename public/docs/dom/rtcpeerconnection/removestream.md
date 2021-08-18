RTCPeerConnection.removeStream()
================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.removeStream()` method removes a [`MediaStream`](../mediastream) as a local source of audio or video. If the negotiation already happened, a new one will be needed for the remote peer to be able to use it. Because this method has been deprecated, you should instead use [`removeTrack()`](removetrack) if your target browser versions have implemented it.

If the [`signalingState`](signalingstate) is set to `"closed"`, an `InvalidStateError` is raised. If the [`signalingState`](signalingstate) is set to `"stable"`, the event `negotiationneeded` is sent on the [`RTCPeerConnection`](../rtcpeerconnection).

Syntax
------

    RTCPeerConnection.removeStream(mediaStream);

### Parameters

`mediaStream`  
A [`MediaStream`](../mediastream) specifying the stream to remove from the connection.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

Example
-------

    var pc, videoStream;
    navigator.getUserMedia({video: true}, function(stream) {
      pc = new RTCPeerConnection();
      videoStream = stream;
      pc.addStream(stream);
    }
    document.getElementById("closeButton").addEventListener("click", function(event) {
      pc.removeStream(videoStream);
      pc.close();
    }, false);

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

`removeStream`

24

15

22-51

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
-   [`RTCPeerConnection.removeTrack()`](removetrack)
-   [`RTCPeerConnection.addTrack()`](addtrack)
-   [`RTCPeerConnection.addStream()`](addstream)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/removeStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/removeStream</a>

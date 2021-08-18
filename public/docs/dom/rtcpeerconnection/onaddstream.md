RTCPeerConnection.onaddstream
=============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `RTCPeerConnection.onaddstream` event handler is a property containing the code to execute when the `addstream` event, of type [`MediaStreamEvent`](../mediastreamevent), is received by this [`RTCPeerConnection`](../rtcpeerconnection). Such an event is sent when a [`MediaStream`](../mediastream) is added to this connection by the remote peer. The event is sent immediately after the call [`setRemoteDescription()`](setremotedescription) and doesn't wait for the result of the SDP negotiation.

**Important:** This property has been **removed** from the specification; you should now use [`RTCPeerConnection.ontrack`](ontrack) to watch for `track` events instead. It is included here in order to help you adapt existing code and understand existing samples, which may not be up-to-date yet.

Syntax
------

    rtcPeerConnection.onaddstream = eventHandler;

### Value

A function which handles `addstream` events. These events, of type [`MediaStreamEvent`](../mediastreamevent), are sent when streams are added to the connection by the remote peer. The first time an event occurs may be nearly immediately after the remote end of the connection is set using [`RTCPeerConnection.setRemoteDescription()`](setremotedescription); it doesn't wait for a particular stream to be accepted or rejected using [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) negotiation.

Example
-------

This code, based on an older version of our [Signaling and video calling](../webrtc_api/signaling_and_video_calling) sample, responds to `addstream` events by setting the video source for a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element to the stream specified in the event, and then enabling a "hang up" button in the app's user interface.

    pc.onaddstream = function(event) {
      document.getElementById("received_video").srcObject = event.stream;
      document.getElementById("hangup-button").disabled = false;
    };

You can also use [`addEventListener()`](../eventtarget/addeventlistener) to add a handler for `addstream` events to an [`RTCPeerConnection`](../rtcpeerconnection).

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

`onaddstream`

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

**Important:** This property has been **removed** from the specification; you should now use [`RTCPeerConnection.ontrack`](ontrack) to watch for `track` events instead. It is included here in order to help you adapt existing code and understand existing samples, which may not be up-to-date yet.

See also
--------

-   Use the newer `track` event, its type [`RTCTrackEvent`](../rtctrackevent), and the [`RTCPeerConnection.ontrack`](ontrack) event handler property instead of this.
-   The `addstream` event and its type, [`MediaStreamEvent`](../mediastreamevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onaddstream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onaddstream</a>

RTCPeerConnection: removestream event
=====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete `removestream` event was sent to an [`RTCPeerConnection`](../rtcpeerconnection) to inform it that a [`MediaStream`](../mediastream) had been removed from the connection. You can use the `RTCPeerConnection` interface's [`onremovestream`](onremovestream) property to set a handler for this event.

This is the counterpart to the [`addstream`](addstream_event) event, which is also obsolete.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../mediastreamevent"><code>MediaStreamEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onremovestream"><code>RTCPeerConnection.onremovestream</code></a></td></tr></tbody></table>

**Important:** This event has been removed from the WebRTC specification in favor of the existing `removetrack` event on the remote [`MediaStream`](../mediastream) and the corresponding [`MediaStream.onremovetrack`](../mediastream/onremovetrack) event handler property of the remote [`MediaStream`](../mediastream). The [`RTCPeerConnection`](../rtcpeerconnection) API is now track-based, so having zero tracks in the remote stream is equivalent to the remote stream being removed, which caused a `removestream` event.

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

`removestream_event`

24

15

22-60

No

43

No

Yes

25

44-60

43

No

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [`RTCPeerConnection.removeStream()`](removestream)
-   [`MediaStream.onremovetrack`](../mediastream/onremovetrack)
-   [`removetrack`](../mediastream/removetrack_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/removestream_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/removestream_event</a>

RTCPeerConnection: addstream event
==================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete `addstream` event is sent to an [`RTCPeerConnection`](../rtcpeerconnection) when new media, in the form of a [`MediaStream`](../mediastream) object, has been added to it.

**Important:** This event has been removed from the WebRTC specification. You should instead watch for the [`track`](track_event) event, which is sent for each media track added to the `RTCPeerConnection`.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../mediastreamevent"><code>MediaStreamEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onaddstream"><code>RTCPeerconnection.onaddstream</code></a></td></tr></tbody></table>

You can, similarly, watch for streams to be removed from the connection by monitoring the [`removestream`](removestream_event) event.

Examples
--------

This example looks to determine if the user's browser supports the [`track`](track_event) event. If it does, a `track` event listener is set up; otherwise, an `addstream` event listener is set up. `pc` is an `RTCPeerConnection`.

    if (pc.addTrack !== undefined) {
      pc.ontrack = ev => {
        ev.streams.forEach(stream => doAddStream(stream));
      }
    } else {
      pc.onaddstream = ev => {
        doAddStream(ev.stream);
      }
    }

This calls a function `doAddStream()` once for each stream being added to the [`RTCPeerConnection`](../rtcpeerconnection), regardless of whether the browser sends `addstream` or `track`.

You can also use the [`addEventListener()`](../eventtarget/addeventlistener) method to set an event listener:

    pc.addEventListener("addstream", ev => doAddStream(ev.stream), false);

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

`addstream_event`

24

15

22

No

43

No

≤37

25

44

43

?

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [`RTCPeerConnection.onaddstream`](onaddstream)
-   [`RTCPeerConnection.addStream()`](addstream)
-   [`MediaStreamEvent`](../mediastreamevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addstream_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/addstream_event</a>

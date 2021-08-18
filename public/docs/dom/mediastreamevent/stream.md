MediaStreamEvent.stream
=======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The read-only property `MediaStreamEvent.stream` returns the [`MediaStream`](../mediastream) associated with the event.

Syntax
------

     var stream = event.stream;

Example
-------

    pc.onaddstream = function( ev ) {
                          alert("A stream (id: '" +
                                ev.stream.id +
                                "') has been added to this connection.");
                       };

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

`stream`

Yes

15

Yes

No

Yes

?

Yes

Yes

?

?

?

Yes

See also
--------

-   `addstream`, `removestream`
-   [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamEvent/stream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamEvent/stream</a>

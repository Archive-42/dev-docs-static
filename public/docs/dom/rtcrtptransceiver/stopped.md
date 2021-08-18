RTCRtpTransceiver.stopped
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The read-only `stopped` property on the [`RTCRtpTransceiver`](../rtcrtptransceiver) interface indicates whether or not the transceiver's associated sender and receiver have both been stopped.

The transceiver is stopped if the [`stop()`](stop) method has been called or if a change to either the local or the remote description has caused the transceiver to be stopped for some reason.

Syntax
------

    var isStopped = RTCRtpTransceiver.stopped;

### Value

A Boolean value which is `true` if the transceiver's [`sender`](sender) will no longer send data, and its [`receiver`](receiver) will no longer receive data. If either or both are still at work, the result is `false`.

Usage notes
-----------

This property is *deprecated* and will be removed in the future. Instead, look at the value of [`currentDirection`](currentdirection). Its value is `stopped` if the transceiver has stopped.

**Note:** Currently only Firefox implements `stopped`, and has not yet been updated to implement this change.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtptransceiver-stopped">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpTransceiver.stopped' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`stopped`

69

No

59

No

No

11

69

69

59

No

11

10.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Introduction to the Real-time Transport Protocol (RTP)](../webrtc_api/intro_to_rtp)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/stopped" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpTransceiver/stopped</a>

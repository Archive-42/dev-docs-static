# MediaStreamTrack.remote

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MediaStreamTrack.remote` read-only property allows Javascript to know whether a WebRTC MediaStreamTrack is from a remote source or a local one. It returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) with a value of `true` if the track is sourced remotely (that is, sourced by an [`RTCPeerConnection`](../rtcpeerconnection)), or `false` if it is sourced locally.

## Syntax

    var bool = track.remote;

## Browser compatibility

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

`remote`

48-59

12-79

Yes

No

35-46

No

48-59

48-59

Yes

35-43

No

5.0-7.0

## See also

- [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/remote" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/remote</a>

RTCPeerConnection.onremovestream
================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `removestream` event has been removed from the WebRTC specification in favor of the existing `removetrack` event on the remote [`MediaStream`](../mediastream) and the corresponding [`MediaStream.onremovetrack`](../mediastream/onremovetrack) event handler property of the remote [`MediaStream`](../mediastream). The [`RTCPeerConnection`](../rtcpeerconnection) API is now track-based, so having zero tracks in the remote stream is equivalent to the remote stream being removed and the old removestream event.

The `RTCPeerConnection.onremovestream` event handler is a property containing the code to execute when the `removestream` event, of type [`MediaStreamEvent`](../mediastreamevent), is received by this [`RTCPeerConnection`](../rtcpeerconnection). Such an event is sent when a [`MediaStream`](../mediastream) is removed from this connection.

Syntax
------

    peerconnection.onremovestream = function;

### Values

-   `function` is the name of a user-defined function, without the `()` suffix or any parameters, or an anonymous function declaration, such as `function(event) {...}`. An event handler always has one single parameter, containing the event, here of type [`MediaStreamEvent`](../mediastreamevent).

Example
-------

    pc.onremovestream = function(ev) { alert("onremovestream event detected!"); };

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

`onremovestream`

24

15

22-60

No

43

Promise-based version.

37-43

No

≤37

Yes

44-60

43

Promise-based version.

37-43

No

6.0

See also
--------

-   The `removestream` event and its type, [`MediaStreamEvent`](../mediastreamevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onremovestream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onremovestream</a>

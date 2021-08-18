RTCPeerConnection.onpeeridentity
================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `RTCPeerConnection.onpeeridentity` event handler is a property containing the code to execute whent the `peeridentity` event, of type [`Event`](../event), is received by this [`RTCPeerConnection`](../rtcpeerconnection). Such an event is sent when an identity assertion, received from a peer, has been successfully validated.

*This event handler is obsolete*. To detect successful validation of the identity, wait for the promise returned by [`peerIdentity`](peeridentity) to resolve successfully with the peer's identity.

Syntax
------

    peerconnection.onpeeridentity = function;

### Values

-   `function` is the name of a user-defined function, without the `()` suffix or any parameters, or an anonymous function declaration, such as `function(event) {...}`. An event handler always has one single parameter, containing the event, here of type [`Event`](../event).

Example
-------

    pc.onpeeridentity = function(ev) { alert("onpeeridentity event detected!"); };

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

`onpeeridentity`

No

≤18-79

22

No

43

Promise-based version.

37-43

No

No

No

44

43

Promise-based version.

37-43

No

6.0

See also
--------

-   The `peeridentity` event and its type, [`Event`](../event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onpeeridentity" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onpeeridentity</a>

RTCPeerConnection.onidpvalidationerror
======================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `RTCPeerConnection.onidpvalidationerror` event handler is a property containing the code to execute whent the `idpvalidationerror` event, of type [`RTCIdentityErrorEvent`](../rtcidentityerrorevent), is received by this [`RTCPeerConnection`](../rtcpeerconnection). Such an event is sent when the associated identity provider (IdP) encounters an error while validating an identity assertion.

*This event handler is obsolete*. You should instead detect IdP validation errors by watching for the [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by [`RTCPeerConnection.peerIdentity`](peeridentity) to be rejected.

Syntax
------

    peerconnection.onidpvalidationerror = function;

### Values

-   `function` is the name of a user-defined function, without the `()` suffix or any parameters, or an anonymous function declaration, such as `function(event) {...}`. An event handler always has one single parameter, containing the event, here of type [`RTCIdentityErrorEvent`](../rtcidentityerrorevent).

Example
-------

    pc.onidpvalidationerror = function(ev) { alert("onidpvalidationerror event detected!"); };

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

`onidpvalidationerror`

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

-   The `idpvalidationerror` event and its type, [`RTCIdentityErrorEvent`](../rtcidentityerrorevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onidpvalidationerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onidpvalidationerror</a>

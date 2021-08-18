RTCIdentityEvent.assertion
==========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The read-only property `RTCIdentityEvent.assertion` returns the [`DOMString`](../domstring) containing a blob being the coded assertion associated with the event.

Firefox implements the interface this property belongs to under the following name: `RTCPeerConnectionIdentityEvent.` It is likely that it will correct this name when it will unprefix [`RTCPeerConnection`](../rtcpeerconnection), once spec and implementation will have been stabilized.

Syntax
------

     var blob = event.assertion;

Example
-------

    pc.onidentityresult = function( ev ) {
                             alert("A new identity assertion (blob: '" +
                                   ev.assertion +
                                   "') has been generated.");
                          }

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

`assertion`

No

No

?

No

Yes

?

No

No

?

?

?

No

See also
--------

-   `identityresult`
-   [`RTCPeerConnection`](../rtcpeerconnection)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityEvent/assertion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIdentityEvent/assertion</a>

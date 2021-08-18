RTCDataChannel.reliable
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The read-only `RTCDataChannel` property `reliable` indicates whether or not the data channel is reliable.

This property is obsolete. Use [`RTCDataChannel.ordered`](ordered) instead in any new code, and update existing code as soon as possible.

Syntax
------

    var reliable = aDataChannel.reliable;

### Value

`true` if the [`RTCDataChannel`](../rtcdatachannel)'s connection is reliable; `false` if it isn't.

Example
-------

    // TBD

Specifications
--------------

No longer part of any specification.

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

`reliable`

56

≤79

No

No

43

No

56

56

No

43

No

6.0

See also
--------

-   [WebRTC](../webrtc_api)
-   [`RTCDataChannel`](../rtcdatachannel)
-   [`RTCDataChannel.ordered`](ordered)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/reliable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/reliable</a>

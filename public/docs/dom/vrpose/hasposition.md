VRPose.hasPosition
==================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `hasPosition` read-only property of the [`VRPose`](../vrpose) interface returns a boolean indicating whether the [`VRPose.position`](position) property is valid (i.e. if the hardware is currently registering a valid position). If it is `false`, the `position` property will return `null`.

Syntax
------

    var myHasPosition = VRPositionState.hasPosition;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Examples
--------

    TBD.

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

`hasPosition`

No

No

No

No

?

No

No

No

?

?

?

No

See also
--------

-   [WebVR API homepage](../webvr_api).
-   <https://mixedreality.mozilla.org/> — demos, downloads, and other resources from the Mozilla VR team.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRPose/hasPosition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRPose/hasPosition</a>

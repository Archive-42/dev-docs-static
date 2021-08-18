VRPose.timestamp
================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `timestamp` read-only property of the [`VRPose`](../vrpose) interface returns the current time stamp of the system — a monotonically increasing value representing the time since the current app was started.

This property is useful for determining if position data has been updated, and what order updates have occurred in.

**Important**: This version of `timestamp` has been removed from the spec — instead, timestamps are returned when [`VRDisplay.getFrameData()`](../vrdisplay/getframedata) is called — see [`VRFrameData.timestamp`](../vrframedata/timestamp).

Syntax
------

    var myTimeStamp = VRPose.timestamp;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) representing the timestamp, in seconds.

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

`timeStamp`

No

15-79

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VRPose/timeStamp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VRPose/timeStamp</a>

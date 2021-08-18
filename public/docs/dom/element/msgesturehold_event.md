Element: MSGestureHold event
============================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `MSGestureHold` event is fired when the user contacts the touch surface and remains in the same position for a while.

It is a proprietary event specific to Microsoft Edge and Internet Explorer.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Unknown</td></tr><tr class="even"><td>Cancelable</td><td>Unknown</td></tr><tr class="odd"><td>Interface</td><td><a href="../msgestureevent"><code>MSGestureEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td>Unknown</td></tr></tbody></table>

The [`UIEvent.detail`](../uievent/detail) property of an `MSGestureHold` event has 3 possible values:

`MSGESTURE_FLAG_BEGIN`  
This value indicates that the user started contacting the touch surface.

`MSGESTURE_FLAG_END`  
This value indicates that the user has stopped touching the touch surface.

 `MSGESTURE_FLAG_END & MSGESTURE_FLAG_CANCEL` (bitwise AND-ed together)  
This value indicates that the user has moved their finger, regardless of whether they also stopped touching the touch surface

Specifications
--------------

Not part of any specification.

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

`MSGestureHold_event`

No

12-79

No

10

No

No

No

No

No

No

No

No

See also
--------

-   Related events:
    -   `MSGestureStart`
    -   `MSGestureEnd`
    -   `MSGestureTap`
    -   `MSGestureChange`
    -   `MSInertiaStart`
    -   `gesturestart`
    -   `gesturechange`
    -   `gestureend`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/MSGestureHold_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/MSGestureHold_event</a>

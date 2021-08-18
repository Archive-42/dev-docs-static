Window.mozInnerScreenX
======================

Summary
-------

Gets the X coordinate of the top-left corner of the window's viewport, in screen coordinates.

**Note:** This coordinate is reported in CSS pixels, not in hardware pixels. That means it can be affected by the zoom level; to compute the actual number of physical screen pixels, you should use the [`nsIDOMWindowUtils.screenPixelsPerCSSPixel`](https://developer.mozilla.org/en-US/docs/XPCOM_Interface_Reference/nsIDOMWindowUtils) property.

Syntax
------

    screenX = window.mozInnerScreenX;

### Value

-   screenX stores the `window.mozInnerScreenX` property value.
-   The `window.mozInnerScreenX` property is a floating point, read-only value; it has no default value.

Specifications
--------------

Not part of any W3C technical specification or recommendation.

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

`mozInnerScreenX`

No

No

3.6

No

No

No

No

No

4

No

No

No

See also
--------

-   [`window.mozInnerScreenY`](mozinnerscreeny)
-   [`nsIDOMWindowUtils.screenPixelsPerCSSPixel`](https://developer.mozilla.org/en-US/docs/XPCOM_Interface_Reference/nsIDOMWindowUtils)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/mozInnerScreenX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/mozInnerScreenX</a>

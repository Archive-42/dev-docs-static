Window.scrollMaxY
=================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Window.scrollMaxY` read-only property returns the maximum number of pixels that the document can be scrolled vertically.

Syntax
------

    yMax = window.scrollMaxY

-   `yMax` is the number of pixels.

Example
-------

    // Scroll to the bottom of the page
    let maxY = window.scrollMaxY;

    window.scrollTo(0, maxY);

Notes
-----

Do not use this property to get the total document height, which is not equivalent to [`window.innerHeight`](innerheight) + window.scrollMaxY, because [`window.innerHeight`](innerheight) includes the width of any visible horizontal scrollbar, thus the result would exceed the total document height by the width of any visible horizontal scrollbar. Instead use [`document.body.scrollHeight`](../element/scrollheight). See also [`window.scrollMaxX`](scrollmaxx) and [`window.scrollTo`](scrollto).

Specifications
--------------

This is not part of any specification.

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

`scrollMaxY`

No

No

1

No

?

No

No

No

4

?

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollMaxY" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollMaxY</a>

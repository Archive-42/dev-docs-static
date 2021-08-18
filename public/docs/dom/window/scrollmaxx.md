Window.scrollMaxX
=================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Window.scrollMaxX` read-only property returns the maximum number of pixels that the document can be scrolled horizontally.

Syntax
------

    xMax = window.scrollMaxX

-   `xMax` is the number of pixels.

Example
-------

    // Scroll to right edge of the page
    let maxX = window.scrollMaxX;

    window.scrollTo(maxX, 0);

Notes
-----

Do not use this property to get the total document width, which is not equivalent to [window.innerWidth](innerwidth) + window.scrollMaxX, because [`window.innerWidth`](innerwidth) includes the width of any visible vertical scrollbar, thus the result would exceed the total document width by the width of any visible vertical scrollbar. Instead use [`document.body.scrollWidth`](../element/scrollwidth). See also [`window.scrollMaxY`](scrollmaxy).

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

`scrollMaxX`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollMaxX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollMaxX</a>

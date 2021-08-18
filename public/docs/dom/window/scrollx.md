Window.scrollX
==============

The read-only `scrollX` property of the [`Window`](../window) interface returns the number of pixels that the document is currently scrolled horizontally. This value is subpixel precise in modern browsers, meaning that it isn't necessarily a whole number. You can get the number of pixels the document is scrolled vertically from the [`scrollY`](scrolly) property.

Syntax
------

    var x = window.scrollX;

### Value

In practice, the returned value is a double-precision floating-point value indicating the number of pixels the document is currently scrolled horizontally from the origin, where a positive value means the content is scrolled to the left. If the document is rendered on a subpixel-precise device, then the returned value is also subpixel-precise and may contain a decimal component. If the document isn't scrolled at all left or right, then `scrollX` is 0.

If you need an integer value, you can use [`Math.round()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round) to round it off.

In more technical terms, `scrollX` returns the X coordinate of the left edge of the current [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport). If there is no viewport, the returned value is 0.

Example
-------

This example checks the current horizontal scroll position of the document. If it's greater than 400 pixels, the window is scrolled back to the beginning.

    if (window.scrollX > 400) {
      window.scroll(0,0);
    }

Notes
-----

<span style="line-height: 1.572;">The </span>`pageXOffset`<span style="line-height: 1.572;"> property is an alias for the </span>`scrollX`<span style="line-height: 1.572;"> property:</span>

    window.pageXOffset == window.scrollX; // always true

For cross-browser compatibility, use `window.pageXOffset` instead of `window.scrollX`. *Additionally*, older versions of Internet Explorer (&lt; 9) do not support either property and must be worked around by checking other non-standard properties. A fully compatible example:

    var x = (window.pageXOffset !== undefined)
      ? window.pageXOffset
      : (document.documentElement || document.body.parentNode || document.body).scrollLeft;

    var y = (window.pageYOffset !== undefined)
      ? window.pageYOffset
      : (document.documentElement || document.body.parentNode || document.body).scrollTop;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-scrollx">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.scrollX' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`scrollX`

1

1

12

12

1

1

9

9.6

4

1

1

1

1

18

18

4

4

10.1

10.1

1

1

1.0

1.0

`subpixel_precision`

Yes

≤18

55

No

Yes

Yes

Yes

Yes

55

?

?

Yes

See also
--------

-   [`Window.scrollY`](scrolly)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollX</a>

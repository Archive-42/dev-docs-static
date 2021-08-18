Window.scrollY
==============

The read-only `scrollY` property of the [`Window`](../window) interface returns the number of pixels that the document is currently scrolled vertically. This value is subpixel precise in modern browsers, meaning that it isn't necessarily a whole number. You can get the number of pixels the document is scrolled horizontally from the [`scrollX`](scrollx) property.

Syntax
------

    var y = window.scrollY

### Value

In practice, the returned value is a double-precision floating-point value indicating the number of pixels the document is currently scrolled vertically from the origin, where a positive value means the content is scrolled to upward. If the document is rendered on a subpixel-precise device, then the returned value is also subpixel-precise and may contain a decimal component. If the document isn't scrolled at all up or down, then `scrollY` is 0.

If you need an integer value, you can use [`Math.round()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round) to round it off.

In more technical terms, `scrollY` returns the Y coordinate of the top edge of the current [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport). If there is no viewport, the returned value is 0.

Example
-------

    // make sure and go down to the second page
    if (window.scrollY) {
      window.scroll(0, 0);  // reset the scroll position to the top left of the document.
    }

    window.scrollByPages(1);

Notes
-----

Use this property to check that the document hasn't already been scrolled when using relative scroll functions such as [`scrollBy()`](scrollby), [`scrollByLines()`](scrollbylines), or [`scrollByPages()`](scrollbypages).

The `pageYOffset` property is an alias for the `scrollY` property:

    window.pageYOffset === window.scrollY; // always true

For cross-browser compatibility, use `window.pageYOffset` instead of `window.scrollY`. **Additionally**, older versions of Internet Explorer (&lt; 9) do not support either property and must be worked around by checking other non-standard properties. A fully compatible example:

    var supportPageOffset = window.pageXOffset !== undefined;
    var isCSS1Compat = ((document.compatMode || "") === "CSS1Compat");

    var x = supportPageOffset ? window.pageXOffset : isCSS1Compat ? document.documentElement.scrollLeft : document.body.scrollLeft;
    var y = supportPageOffset ? window.pageYOffset : isCSS1Compat ? document.documentElement.scrollTop : document.body.scrollTop;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-scrolly">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.scrollY' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`scrollY`

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

-   [`window.scrollX`](scrollx)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollY" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollY</a>

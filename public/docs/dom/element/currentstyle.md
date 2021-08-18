Element.currentStyle
====================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`Element.currentStyle` is a proprietary property which is similar to the standardized [`window.getComputedStyle()`](../window/getcomputedstyle) method. It is available in old versions of Microsoft Internet Explorer. However, it returns the units set in CSS while `window.getComputedStyle()` returns the values in pixels.

Polyfill
--------

This polyfill returns the values in pixels and is likely to be rather slow, as it has to call [`window.getComputedStyle()`](../window/getcomputedstyle) every time its value is read.

    /* Any copyright is dedicated to the Public Domain.
     * http://creativecommons.org/publicdomain/zero/1.0/ */

    if (!("currentStyle" in Element.prototype)) {
      Object.defineProperty(Element.prototype, "currentStyle", {
        get: function() {
          return window.getComputedStyle(this);
        }
      });
    }

Specifications
--------------

Not part of any specification.

Microsoft [had a description on MSDN](https://web.archive.org/web/20150629144515/https://msdn.microsoft.com/en-us/library/ms535231(v=vs.85).aspx).

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

`currentStyle`

No

No

No

5

≤12.1-15

No

No

No

No

≤12.1-14

No

No

See also
--------

-   [`Element.runtimeStyle`](runtimestyle)
-   [`window.getComputedStyle()`](../window/getcomputedstyle)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/currentStyle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/currentStyle</a>

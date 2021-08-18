Element.scrollIntoViewIfNeeded()
================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Element.scrollIntoViewIfNeeded()` method scrolls the current element into the visible area of the browser window if it's not already within the visible area of the browser window. If the element is already within the visible area of the browser window, then no scrolling takes place. This method is a proprietary variation of the standard [`Element.scrollIntoView()`](scrollintoview) method.

Syntax
------

TODO

### Parameters

*`opt_center`*  
Is an optional [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value with a default value of `true`:

-   If `true`, the element will be aligned so it is centered within the visible area of the scrollable ancestor.
-   If `false`, the element will be aligned to the nearest edge of the visible area of the scrollable ancestor. Depending on which edge of the visible area is closest to the element, either the top of the element will be aligned to the top edge of the visible area, or the bottom edge of the element will be aligned to the bottom edge of the visible area.

Example
-------

    var element = document.getElementById("my-el");

    element.scrollIntoViewIfNeeded();
    element.scrollIntoViewIfNeeded(true); // Centers the element in the visible area

Specifications
--------------

Not part of any specification. This is a proprietary, WebKit-specific method.

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

`scrollIntoViewIfNeeded`

1

79

No

No

15

3

1

18

No

14

1

1.0

See also
--------

-   [W3C CSSOM bug 17152: Support centering an element when scrolling into view.](https://www.w3.org/Bugs/Public/show_bug.cgi?id=17152) (feature request for a standardized equivalent to `scrollIntoViewIfNeeded`)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoViewIfNeeded" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoViewIfNeeded</a>

Element.scrollTop
=================

The `Element.scrollTop` property gets or sets the number of pixels that an element's content is scrolled vertically.

An element's `scrollTop` value is a measurement of the distance from the element's top to its topmost *visible* content. When an element's content does not generate a vertical scrollbar, then its `scrollTop` value is `0`.

When `scrollTop` is used on the root element (the `<html>` element), the `scrollY` of the window is returned. [This is a special case of `scrollTop`](https://www.w3.org/TR/2016/WD-cssom-view-1-20160317/#dom-element-scrolltop).

On systems using display scaling, `scrollTop` may give you a decimal value.

Syntax
------

    // Get the number of pixels scrolled.
    var intElemScrollTop = someElement.scrollTop;

After running this code, `intElemScrollTop` is an integer corresponding to the number of pixels that the [`element`](../element)'s content has been scrolled upwards.

    // Set the number of pixels scrolled.
    element.scrollTop = intValue;

`scrollTop` can be set to any integer value, with certain caveats:

-   If the element can't be scrolled (e.g. it has no overflow or if the element has a property of "**non-scrollable**"), `scrollTop` is `0`.
-   `scrollTop` doesn't respond to negative values; instead, it sets itself back to `0`.
-   If set to a value greater than the maximum available for the element, `scrollTop` settles itself to the maximum value.

Example
-------

padding-top

***If you can see this, scrollTop = 0***

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

***If you can see this, scrollTop is &gt; 0***

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

***If you can see this, scrollTop is maxed-out***

padding-bottom

**Left** **Top** **Right** **Bottom** *margin-top* *margin-bottom* *border-top* *border-bottom*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-scrolltop">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'scrollTop' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`scrollTop`

1

12

1

5

8

1

1

18

4

10.1

1

1.0

See also
--------

-   [MSDN's Measuring Element Dimension and Location](https://msdn.microsoft.com/en-us/library/hh781509(v=vs.85).aspx)
-   [`Element.scrollLeft`](scrollleft)
-   [`Element.scrollTo()`](scrollto)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop</a>

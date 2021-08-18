IntersectionObserverEntry.boundingClientRect
============================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`IntersectionObserverEntry`](../intersectionobserverentry) interface's read-only `boundingClientRect` property returns a [`DOMRectReadOnly`](../domrectreadonly) which in essence describes a rectangle describing the smallest rectangle that contains the entire target element.

Syntax
------

    var boundsRect = IntersectionObserverEntry.boundingClientRect;

### Value

A [`DOMRectReadOnly`](../domrectreadonly) which describes the smallest rectangle that contains every part of the target element whose intersection change is being described. This value is obtained using the same algorithm as [`Element.getBoundingClientRect()`](../element/getboundingclientrect), so refer to that article for details on precisely what is done to obtain this rectangle and what is and is not included within its bounds.

In the general case, however, it's safe to think of this as the bounds rectangle of the target element.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserverentry-boundingclientrect">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserverEntry.boundingClientRect' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`boundingClientRect`

51

15

55

No

Yes

12.1

51

51

55

?

12.2

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/boundingClientRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/boundingClientRect</a>

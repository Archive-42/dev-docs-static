IntersectionObserverEntry.intersectionRect
==========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`IntersectionObserverEntry`](../intersectionobserverentry) interface's read-only `intersectionRect` property is a [`DOMRectReadOnly`](../domrectreadonly) object which describes the smallest rectangle that contains the entire portion of the target element which is currently visible within the intersection root.

Syntax
------

    var intersectionRect = IntersectionObserverEntry.intersectionRect;

### Value

A [`DOMRectReadOnly`](../domrectreadonly) which describes the part of the target element that's currently visible within the root's intersection rectangle.

This rectangle is computed by taking the intersection of [`boundingClientRect`](../intersectionobserverentry) with each of the [`target`](target)'s ancestors' clip rectangles, with the exception of the intersection [`root`](../intersectionobserver/root) itself.

Example
-------

In this simple example, an intersection callback stores the intersection rectangle for later use by the code that draws the target elements' contents, so that only the visible area is redrawn.

    function intersectionCallback(entries) {
      entries.forEach(function(entry) {
        refreshZones.push({
          element: entry.target,
          rect: entry.intersectionRect
        });
      });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserverentry-intersectionrect">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserverEntry.intersectionRect' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`intersectionRect`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/intersectionRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/intersectionRect</a>

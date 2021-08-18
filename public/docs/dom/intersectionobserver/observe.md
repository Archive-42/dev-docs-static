IntersectionObserver.observe()
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`IntersectionObserver`](../intersectionobserver) method `observe()` adds an element to the set of target elements being watched by the `IntersectionObserver`. One observer has one set of thresholds and one root, but can watch multiple target elements for visibility changes in keeping with those. To stop observing the element, call [`IntersectionObserver.unobserve()`](unobserve).

When the visibility of the specified element crosses over one of the observer's visibility thresholds (as listed in [`IntersectionObserver.thresholds`](thresholds)), the observer's callback is executed with an array of [`IntersectionObserverEntry`](../intersectionobserverentry) objects representing the intersection changes which occurred. Note that this design allows multiple elements' intersection changes to be processed by a single call to the callback.

Syntax
------

    IntersectionObserver.observe(targetElement);

### Parameters

`targetElement`  
An [`element`](../element) whose visibility within the root is to be monitored. This element must be a descendant of the root element (or contained within the current document, if the root is the document's viewport).

### Return value

`undefined`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserver-observe">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserver.observe()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`observe`

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

See also
--------

-   [`IntersectionObserver.unobserve()`](unobserve)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/observe" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/observe</a>

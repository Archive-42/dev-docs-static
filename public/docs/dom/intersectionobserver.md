IntersectionObserver
====================

The `IntersectionObserver` interface of the [Intersection Observer API](intersection_observer_api) provides a way to asynchronously observe changes in the intersection of a target element with an ancestor element or with a top-level document's [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport). The ancestor element or viewport is referred to as the root.

When an `IntersectionObserver` is created, it's configured to watch for given ratios of visibility within the root. The configuration cannot be changed once the `IntersectionObserver` is created, so a given observer object is only useful for watching for specific changes in degree of visibility; however, you can watch multiple target elements with the same observer.

Constructor
-----------

[`IntersectionObserver.IntersectionObserver()`](intersectionobserver/intersectionobserver)  
Creates a new `IntersectionObserver` object which will execute a specified callback function when it detects that a target element's visibility has crossed one or more thresholds.

Properties
----------

 [`IntersectionObserver.root`](intersectionobserver/root) <span class="badge inline readonly">Read only </span>   
The [`Element`](element) or [`Document`](document) whose bounds are used as the bounding box when testing for intersection. If no `root` value was passed to the constructor or its value is `null`, the top-level document's viewport is used.

 [`IntersectionObserver.rootMargin`](intersectionobserver/rootmargin) <span class="badge inline readonly">Read only </span>   
An offset rectangle applied to the root's [bounding box](https://developer.mozilla.org/en-US/docs/Glossary/bounding_box) when calculating intersections, effectively shrinking or growing the root for calculation purposes. The value returned by this property may not be the same as the one specified when calling the constructor as it may be changed to match internal requirements. Each offset can be expressed in pixels (`px`) or as a percentage (`%`). The default is "0px 0px 0px 0px".

 [`IntersectionObserver.thresholds`](intersectionobserver/thresholds) <span class="badge inline readonly">Read only </span>   
A list of thresholds, sorted in increasing numeric order, where each threshold is a ratio of intersection area to bounding box area of an observed target. Notifications for a target are generated when any of the thresholds are crossed for that target. If no value was passed to the constructor, 0 is used.

Methods
-------

[`IntersectionObserver.disconnect()`](intersectionobserver/disconnect)  
Stops the `IntersectionObserver` object from observing any target.

[`IntersectionObserver.observe()`](intersectionobserver/observe)  
Tells the `IntersectionObserver` a target element to observe.

[`IntersectionObserver.takeRecords()`](intersectionobserver/takerecords)  
Returns an array of [`IntersectionObserverEntry`](intersectionobserverentry) objects for all observed targets.

[`IntersectionObserver.unobserve()`](intersectionobserver/unobserve)  
Tells the `IntersectionObserver` to stop observing a particular target element.

Examples
--------

    var intersectionObserver = new IntersectionObserver(function(entries) {
      // If intersectionRatio is 0, the target is out of view
      // and we do not need to do anything.
      if (entries[0].intersectionRatio <= 0) return;

      loadItems(10);
      console.log('Loaded new items');
    });
    // start observing
    intersectionObserver.observe(document.querySelector('.scrollerFooter'));

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#intersection-observer-interface">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserver' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`IntersectionObserver`

51

15

55

No

38

12.1

51

51

55

41

12.2

5.0

`IntersectionObserver`

51

15

55

No

38

12.1

51

51

55

?

12.2

5.0

`disconnect`

51

15

Available since [Windows Insider Preview Build 14986](https://developer.microsoft.com/microsoft-edge/platform/status/intersectionobserver/)

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

`root`

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

`rootMargin`

51

15

55

No

Yes

12.1

`rootMargin` does not work with `<iframe>`s.

51

51

55

?

12.2

`rootMargin` does not work with `<iframe>`s.

5.0

`takeRecords`

51

15

Available since [Windows Insider Preview Build 14986](https://developer.microsoft.com/microsoft-edge/platform/status/intersectionobserver/)

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

`thresholds`

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

`unobserve`

51

15

Available since [Windows Insider Preview Build 14986](https://developer.microsoft.com/microsoft-edge/platform/status/intersectionobserver/)

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

-   [`MutationObserver`](mutationobserver)
-   [`PerformanceObserver`](performanceobserver)
-   [`ResizeObserver`](resizeobserver)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver</a>

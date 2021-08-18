IntersectionObserver.takeRecords()
==================================

The [`IntersectionObserver`](../intersectionobserver) method `takeRecords()` returns an array of [`IntersectionObserverEntry`](../intersectionobserverentry) objects, one for each targeted element which has experienced an intersection change since the last time the intersections were checked, either explicitly through a call to this method or implicitly by an automatic call to the observer's callback.

**Note:** If you use the callback to monitor these changes, you don't need to call this method. Calling this method clears the pending intersection list, so the callback will not be run.

Syntax
------

    intersectionObserverEntries = intersectionObserver.takeRecords();

### Parameters

None.

### Return value

An array of [`IntersectionObserverEntry`](../intersectionobserverentry) objects, one for each target element whose intersection with the root has changed since the last time the intersections were checked.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserver-takerecords">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserver.takeRecords()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [Intersection Observer API](../intersection_observer_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/takeRecords" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/takeRecords</a>

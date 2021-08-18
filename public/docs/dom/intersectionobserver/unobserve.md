# IntersectionObserver.unobserve()

The [`IntersectionObserver`](../intersectionobserver) method `unobserve()` instructs the `IntersectionObserver` to stop observing the specified target element.

## Syntax

    IntersectionObserver.unobserve(target);

### Parameters

`target`  
The [`Element`](../element) to cease observing. If the specified element isn't being observed, this method does nothing and no exception is thrown.

### Return value

`undefined`.

## Example

This snippet shows an observer being created, an element being observed, and then being unobserved.

    var observer = new IntersectionObserver(callback);
    observer.observe(document.getElementById("elementToObserve"));

    /* ... */

    observer.unobserve(document.getElementById("elementToObserve"));

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserver-unobserve">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserver.unobserve()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

## See also

- [Intersection Observer API](../intersection_observer_api)
- [`IntersectionObserver.observe()`](observe)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/unobserve" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/unobserve</a>

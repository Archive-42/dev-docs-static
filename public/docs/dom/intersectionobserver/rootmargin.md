# IntersectionObserver.rootMargin

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`IntersectionObserver`](../intersectionobserver) interface's read-only `rootMargin` property is a string with syntax similar to that of the CSS [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) property. Each side of the rectangle represented by `rootMargin` is added to the corresponding side in the [`root`](root) element's [bounding box](https://developer.mozilla.org/en-US/docs/Glossary/bounding_box) before the intersection test is performed. This lets you, for example, adjust the bounds outward so that the target element is considered 100% visible even if a certain number of pixels worth of width or height is clipped away, or treat the target as partially hidden if an edge is too close to the edge of the root's bounding box.

See [The root element and root margin](#) in [Intersection Observer API](../intersection_observer_api) for a more in-depth look at the root margin and how it works with the root's bounding box.

## Syntax

    var marginString = IntersectionObserver.rootMargin;

### Value

A string, formatted similarly to the CSS [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) property's value, which contains offsets for one or more sides of the root's bounding box. These offsets are added to the corresponding values in the root's bounding box before the intersection between the resulting rectangle and the target element's bounds.

The string returned by this property may not match the one specified when the [`IntersectionObserver`](../intersectionobserver) was instantiated. The browser is permitted to alter the values

If `rootMargin` isn't specified when the object was instantiated, it defaults to the string `"0px 0px 0px 0px"`, meaning that the intersection will be computed between the root element's unmodified bounds rectangle and the target's bounds. [The root element and root margin](#) in [Intersection Observer API](../intersection_observer_api) describes how the `rootMargin` is used in more detail.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserverinit-rootmargin">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserver.rootMargin' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/rootMargin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/rootMargin</a>

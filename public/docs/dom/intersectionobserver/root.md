# IntersectionObserver.root

The [`IntersectionObserver`](../intersectionobserver) interface's read-only `root` property identifies the [`Element`](../element) or [`Document`](../document) whose bounds are treated as the [bounding box](https://developer.mozilla.org/en-US/docs/Glossary/bounding_box) of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) for the element which is the observer's target. If the `root` is `null`, then the bounds of the actual document viewport are used.

## Syntax

    var root = intersectionObserver.root;

### Value

A [`Element`](../element) or [`Document`](../document) object whose bounding box is used as the bounds of the viewport for the purposes of determining how much of the target element is visible. The intersection of this bounding rectangle, offset by any margins specified in the options passed to the [`IntersectionObserver()`](intersectionobserver) constructor, the target element's bounds, minus the bounds of every element or other object which overlaps the target element, is considered to be the visible area of the target element.

If `root` is `null`, then the owning document is used as the root, and the bounds its viewport (that is, the visible area of the document) are used as the root bounds.

## Example

This example sets the [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) of the intersection observer's root element to be a 2-pixel medium green line.

    observer.root.style.border = "2px solid #44aa44";

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserver-root">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserver' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [Timing element visibility with the Intersection Observer API](../intersection_observer_api/timing_element_visibility)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/root" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/root</a>

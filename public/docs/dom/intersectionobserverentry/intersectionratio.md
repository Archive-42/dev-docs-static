# IntersectionObserverEntry.intersectionRatio

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`IntersectionObserverEntry`](../intersectionobserverentry) interface's read-only `intersectionRatio` property tells you how much of the target element is currently visible within the root's intersection ratio, as a value between 0.0 and 1.0.

## Syntax

    var intersectionRatio = IntersectionObserverEntry.intersectionRatio;

### Value

A number between 0.0 and 1.0 which indicates how much of the target element is actually visible within the root's intersection rectangle. More precisely, this value is the ratio of the area of the intersection rectangle ([`intersectionRect`](intersectionrect)) to the area of the target's bounds rectangle ([`boundingClientRect`](boundingclientrect)).

If the area of the target's bounds rectangle is zero, the returned value is 1 if [`isIntersecting`](isintersecting) is `true` or 0 if not.

## Example

In this simple example, an intersection callback sets each target element's [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity) to the intersection ratio of that element with the root.

    function intersectionCallback(entries) {
      entries.forEach(function(entry) {
        entry.target.style.opacity = entry.intersectionRatio;
      });
    }

To see a more concrete example, take a look at [Handling intersection changes](../intersection_observer_api/timing_element_visibility#handling_intersection_changes) in [Timing element visibility with the Intersection Observer API](../intersection_observer_api/timing_element_visibility).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserverentry-intersectionratio">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserverEntry.intersectionratio' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`intersectionRatio`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/intersectionRatio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/intersectionRatio</a>

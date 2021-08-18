# IntersectionObserverEntry.isIntersecting

The [`IntersectionObserverEntry`](../intersectionobserverentry) interface's read-only `isIntersecting` property is a Boolean value which is `true` if the target element intersects with the intersection observer's root. If this is `true`, then, the `IntersectionObserverEntry` describes a transition into a state of intersection; if it's `false`, then you know the transition is from intersecting to not-intersecting.

## Syntax

    var isIntersecting = IntersectionObserverEntry.isIntersecting;

### Value

A Boolean value which indicates whether the [`target`](target) element has transitioned into a state of intersection (`true`) or out of a state of intersection (`false`).

## Example

In this simple example, an intersection callback is used to update a counter of how many targeted elements are currently intersecting with the [intersection root](../intersectionobserver/root).

    function intersectionCallback(entries) {
      entries.forEach(function(entry) {
        if (entry.isIntersecting) {
          intersectingCount += 1;
        } else {
          intersectingCount -= 1;
        }
      });
    }

To see a more concrete example, take a look at [Handling intersection changes](../intersection_observer_api/timing_element_visibility#handling_intersection_changes) in [Timing element visibility with the Intersection Observer API](../intersection_observer_api/timing_element_visibility).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserverentry-isintersecting">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserverEntry.isIntersecting' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`isIntersecting`

51

16

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/isIntersecting" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/isIntersecting</a>

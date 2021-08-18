# IntersectionObserverEntry.target

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`IntersectionObserverEntry`](../intersectionobserverentry) interface's read-only `target` property indicates which targeted [`Element`](../element) has changed its amount of intersection with the intersection root.

## Syntax

    var target = IntersectionObserverEntry.target;

### Value

The `IntersectionObserverEntry`'s `target` property specifies which [`Element`](../element) previously targeted by calling [`IntersectionObserver.observe()`](../intersectionobserver/observe) experienced a change in intersection with the root.

## Example

In this simple example, each targeted element's [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity) is set to its [`intersectionRatio`](intersectionratio).

    function intersectionCallback(entries) {
      entries.forEach(function(entry) {
        entry.target.opacity = entry.intersectionRatio;
      });
    }

To see a more concrete example, take a look at [Handling intersection changes](../intersection_observer_api/timing_element_visibility#handling_intersection_changes) in [Timing element visibility with the Intersection Observer API](../intersection_observer_api/timing_element_visibility).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserverentry-target">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserverEntry.target' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`target`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/target" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/target</a>

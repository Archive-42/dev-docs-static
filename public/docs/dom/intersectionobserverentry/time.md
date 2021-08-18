# IntersectionObserverEntry.time

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`IntersectionObserverEntry`](../intersectionobserverentry) interface's read-only `time` property is a [`DOMHighResTimeStamp`](../domhighrestimestamp) that indicates the time at which the intersection change occurred relative to the time at which the document was created.

## Syntax

    var time = IntersectionObserverEntry.time;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) which indicates the time at which the [`target`](target) element experienced the intersection change described by the `IntersectionObserverEntry`. The time is specified in milliseconds since the creation of the containing document.

## Example

See [Timing element visibility with the Intersection Observer API](../intersection_observer_api/timing_element_visibility) for a complete example which uses the `time` property to track how long elements are visible to the user.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#dom-intersectionobserverentry-time">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserverEntry.time' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`time`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/time" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry/time</a>

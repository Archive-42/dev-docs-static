# IntersectionObserverEntry

The `IntersectionObserverEntry` interface of the [Intersection Observer API](intersection_observer_api) describes the intersection between the target element and its root container at a specific moment of transition. Instances of `IntersectionObserverEntry` are delivered to an [`IntersectionObserver`](intersectionobserver) callback in its `entries` parameter; otherwise, these objects can only be obtained by calling [`IntersectionObserver.takeRecords()`](intersectionobserver/takerecords).

## Properties

[`IntersectionObserverEntry.boundingClientRect`](intersectionobserverentry/boundingclientrect) <span class="badge inline readonly">Read only </span>  
Returns the bounds rectangle of the target element as a [`DOMRectReadOnly`](domrectreadonly). The bounds are computed as described in the documentation for [`Element.getBoundingClientRect()`](element/getboundingclientrect).

[`IntersectionObserverEntry.intersectionRatio`](intersectionobserverentry/intersectionratio) <span class="badge inline readonly">Read only </span>  
Returns the ratio of the `intersectionRect` to the `boundingClientRect`.

[`IntersectionObserverEntry.intersectionRect`](intersectionobserverentry/intersectionrect) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMRectReadOnly`](domrectreadonly) representing the target's visible area.

[`IntersectionObserverEntry.isIntersecting`](intersectionobserverentry/isintersecting) <span class="badge inline readonly">Read only </span>  
A Boolean value which is `true` if the target element intersects with the intersection observer's root. If this is `true`, then, the `IntersectionObserverEntry` describes a transition into a state of intersection; if it's `false`, then you know the transition is from intersecting to not-intersecting.

[`IntersectionObserverEntry.rootBounds`](intersectionobserverentry/rootbounds) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMRectReadOnly`](domrectreadonly) for the intersection observer's root.

[`IntersectionObserverEntry.target`](intersectionobserverentry/target) <span class="badge inline readonly">Read only </span>  
The [`Element`](element) whose intersection with the root changed.

[`IntersectionObserverEntry.time`](intersectionobserverentry/time) <span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) indicating the time at which the intersection was recorded, relative to the `IntersectionObserver`'s [time origin](domhighrestimestamp#the_time_origin).

## Methods

_This interface has no methods._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/IntersectionObserver/#intersection-observer-entry">Intersection Observer<br />
<span class="small">The definition of 'IntersectionObserverEntry' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`IntersectionObserverEntry`

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

`IntersectionObserverEntry`

No

15-79

No

No

No

12.1

No

No

No

No

12.2

No

`boundingClientRect`

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

`intersectionRect`

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

`rootBounds`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry</a>

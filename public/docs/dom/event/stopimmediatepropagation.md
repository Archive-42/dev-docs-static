# Event.stopImmediatePropagation()

The `stopImmediatePropagation()` method of the [`Event`](../event) interface prevents other listeners of the same event from being called.

If several listeners are attached to the same element for the same event type, they are called in the order in which they were added. If `stopImmediatePropagation()` is invoked during one such call, no remaining listeners will be called.

## Syntax

    event.stopImmediatePropagation();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-stopimmediatepropagation">DOM<br />
<span class="small">The definition of 'Event.stopImmediatePropagation()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`stopImmediatePropagation`

6

12

10

9

15

5

≤37

18

10

14

5

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/stopImmediatePropagation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/stopImmediatePropagation</a>

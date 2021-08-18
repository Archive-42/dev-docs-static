Event.stopPropagation()
=======================

The `stopPropagation()` method of the [`Event`](../event) interface prevents further propagation of the current event in the capturing and bubbling phases. It does not, however, prevent any default behaviors from occurring; for instance, clicks on links are still processed. If you want to stop those behaviors, see the [`preventDefault()`](preventdefault) method.

Syntax
------

    event.stopPropagation();

### Parameters

None.

### Return value

`undefined`.

Examples
--------

See Example 5: [Event Propagation](../document_object_model/examples#example_5_event_propagation) in the Examples chapter for a more detailed example of this method and event propagation in the DOM.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-stoppropagation">DOM<br />
<span class="small">The definition of 'Event.stopPropagation()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#dom-event-stoppropagation">DOM4<br />
<span class="small">The definition of 'Event.stopPropagation()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-stopPropagation">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.stopPropagation()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`stopPropagation`

1

12

1

9

7

1

1

18

4

10.1

1

1.0

See also
--------

-   See the [DOM specification](https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-flow-capture) for the explanation of event flow. The [DOM Level 3 Events draft](https://www.w3.org/TR/DOM-Level-3-Events/#event-flow) has an illustration.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation</a>

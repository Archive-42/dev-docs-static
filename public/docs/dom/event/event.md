Event()
=======

The `Event()` constructor creates a new [`Event`](../event).

Syntax
------

    new Event(typeArg[, eventInit]);

### Values

`typeArg`  
This is a [`DOMString`](../domstring) representing the name of the event.

 `eventInit` <span class="badge inline optional">Optional</span>   
This is an `EventInit` dictionary, having the following optional fields:

 `bubbles` <span class="badge inline optional">Optional</span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event bubbles. The default is `false`.

 `cancelable` <span class="badge inline optional">Optional</span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event can be cancelled. The default is `false`.

 `composed` <span class="badge inline optional">Optional</span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the event will trigger listeners outside of a shadow root (see [`Event.composed`](composed) for more details). The default is `false`.

Example
-------

    // create a look event that bubbles up and cannot be canceled

    const evt = new Event("look", {"bubbles":true, "cancelable":false});
    document.dispatchEvent(evt);

    // event can be dispatched from any element, not only the document
    myDiv.dispatchEvent(evt);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-event">DOM<br />
<span class="small">The definition of 'Event()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`Event`

15

12

11

No

11.6

6

≤37

18

14

12

6

1.0

See also
--------

-   [`Event`](../event)
-   [`EventTarget.dispatchEvent()`](../eventtarget/dispatchevent)
-   [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/Event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/Event</a>

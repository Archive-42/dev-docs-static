# EventListener.handleEvent()

The [`EventListener`](../eventlistener) method `handleEvent()` method is called by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) when an event is sent to the `EventListener`, in order to handle events that occur on an observed [`EventTarget`](../eventtarget).

## Syntax

    eventListener.handleEvent(event);

### Parameters

`event`  
An [`Event`](../event) object describing the event that has been fired and needs to be processed.

### Return value

`undefined`. If you return a value, the browser will ignore it.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-eventlistener-handleevent">DOM<br />
<span class="small">The definition of 'EventListener.handleEvent()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-EventListener-handleEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'EventListener.handleEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`handleEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventListener/handleEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventListener/handleEvent</a>

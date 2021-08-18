# Event.type

The `type` read-only property of the [`Event`](../event) interface returns a string containing the event's type. It is set when the event is constructed and is the name commonly used to refer to the specific event, such as `click`, `load`, or `error`.

For a list of available event types, see the [event reference](https://developer.mozilla.org/en-US/docs/Web/Events).

## Syntax

    let eventType = event.type;

### Value

A [`DOMString`](../domstring) containing the type of [`Event`](../event).

## Example

This example logs the event type whenever you press a keyboard key or click a mouse button.

### HTML

    <p>Press any key or click the mouse to get the event type.</p>
    <p id="log"></p>

### JavaScript

    function getEventType(event) {
      const log = document.getElementById('log');
      log.innerText = event.type + '\n' + log.innerText;
    }

    // Keyboard events
    document.addEventListener('keydown', getEventType, false);  // first
    document.addEventListener('keypress', getEventType, false); // second
    document.addEventListener('keyup', getEventType, false);    // third

    // Mouse events
    document.addEventListener('mousedown', getEventType, false); // first
    document.addEventListener('mouseup', getEventType, false);   // second
    document.addEventListener('click', getEventType, false);     // third

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-type">DOM<br />
<span class="small">The definition of 'Event.type' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-type">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.type' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`type`

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

## See also

- [`EventTarget.addEventListener()`](../eventtarget/addeventlistener)
- [`EventTarget.removeEventListener()`](../eventtarget/removeeventlistener)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/type</a>

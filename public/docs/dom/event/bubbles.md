# Event.bubbles

The `bubbles` read-only property of the [`Event`](../event) interface indicates whether the event bubbles up through the DOM or not.

**Note**: See [Event bubbling and capture](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#event_bubbling_and_capture) for more information on bubbling.

## Syntax

    var doesItBubble = event.bubbles;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), which is `true` if the event bubbles up through the DOM.

## Example

    function handleInput(e) {
      // Checks whether the event bubbles and ...
      if (!e.bubbles) {
        // ... passes the event along if does not
        passItOn(e);
      }

      // Already bubbling
      doOutput(e);
    }

**Note**: Only certain events can bubble. Events that do bubble have this property set to `true`. You can use this property to check if an event is allowed to bubble or not.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-bubbles">DOM<br />
<span class="small">The definition of 'Event.bubbles' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-canBubble">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.bubbles' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`bubbles`

Yes

12

Yes

?

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

## See also

- [`stopPropagation()`](stoppropagation) to prevent further propagation of the current event in the capturing and bubbling phases
- [`stopImmediatePropagation()`](stopimmediatepropagation) to not call any further listeners for the same event at the same level in the DOM
- [`preventDefault()`](preventdefault) to allow propagation to continue but to disallow the browser to perform its default action should no listeners handle the event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/bubbles" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/bubbles</a>

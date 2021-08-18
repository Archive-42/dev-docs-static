# Event.cancelable

The **`cancelable`** read-only property of the [`Event`](../event) interface indicates whether the event can be canceled, and therefore prevented as if the event never happened. If the event is _not_ cancelable, then its `cancelable` property will be `false` and the event listener cannot stop the event from occurring.

Event listeners that handle multiple kinds of events may want to check `cancelable` before invoking their [`preventDefault()`](preventdefault) methods.

Most browser-native events that can be canceled are the ones that result from the user interacting with the page. Canceling the [`click`](../element/click_event), [`scroll`](../document/scroll_event), or [`beforeunload`](../window/beforeunload_event) events would prevent the user from clicking on something, scrolling the page, or navigating away from the page, respectively.

[Custom events](event) created by other JavaScript code control if they can be canceled when they are created.

## Syntax

    bool = event.cancelable;

### Value

The result is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), which is `true` if the event can be canceled.

## Example

For example, browser vendors are proposing that the [`wheel`](../document/wheel_event) event can only be canceled [the first time the listener is called](https://github.com/WICG/interventions/issues/33) — any following `wheel` events cannot be canceled.

    function preventScrollWheel(event) {
      if (typeof event.cancelable !== 'boolean' || event.cancelable) {
        // The event can be canceled, so we do so.
        event.preventDefault();
      } else {
        // The event cannot be canceled, so it is not safe
        // to call preventDefault() on it.
        console.warn(`The following event couldn't be canceled:`);
        console.dir(event);
      }
    }

    document.addEventListener('wheel', preventScrollWheel);

## Notes

Whether an event can be canceled or not is something that's determined when that event is initialized.

To cancel an event, call the [`preventDefault()`](preventdefault) method on the event. This keeps the implementation from executing the default action that is associated with the event.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-cancelable">DOM<br />
<span class="small">The definition of 'Event.cancelable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-canCancel">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.cancelable' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`cancelable`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelable</a>

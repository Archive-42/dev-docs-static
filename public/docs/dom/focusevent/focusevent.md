# FocusEvent()

The `FocusEvent()` constructor returns a newly created [`FocusEvent`](../focusevent) object with an optional [`EventTarget`](../eventtarget). When the event has both a source and a destination, the `relatedTarget` value must be set to the other target.

## Syntax

    var focusEvent = new FocusEvent(typeArg[, focusEventInit]);

### Properties

_The `FocusEvent()` constructor also inherits arguments from [`UIEvent()`](../uievent/uievent) and from [`Event()`](../event/event)._

`typeArg`  
Is a [`DOMString`](../domstring) representing the name of the event.

`focusEventInit` <span class="badge inline optional">Optional</span>  
Is a `FocusEventInit` dictionary, having the following fields:

- `"relatedTarget"`, optional and defaulting to `null`, is an [`EventTarget`](../eventtarget) representing the secondary target of a [`FocusEvent`](../focusevent).

The `FocusEventInit` dictionary also accepts fields from the [`UIEventInit`](../uievent/uievent) and [`EventInit`](../event/event) dictionaries.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-FocusEvent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'FocusEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`FocusEvent`

Yes

12

24

No

Yes

Yes

Yes

Yes

24

Yes

Yes

Yes

## See also

- The [`FocusEvent`](../focusevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent/FocusEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent/FocusEvent</a>

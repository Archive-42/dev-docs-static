# FocusEvent

The `FocusEvent` interface represents focus-related events, including [`focus`](element/focus_event), [`blur`](element/blur_event), [`focusin`](element/focusin_event), and [`focusout`](element/focusout_event).

## Constructor

[`FocusEvent()`](focusevent/focusevent)  
Creates a `FocusEvent` event with the given parameters.

## Properties

_This interface also inherits properties from its parent [`UIEvent`](uievent), and indirectly from [`Event`](event)_.

[`FocusEvent.relatedTarget`](focusevent/relatedtarget)  
Is an [`EventTarget`](eventtarget) representing a secondary target for this event. In some cases (such as when tabbing in or out a page), this property may be set to `null` for security reasons.

## Methods

_This interface has no specific methods. It inherits methods from its parent [`UIEvent`](uievent), and indirectly from [`Event`](event)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#interface-focusevent">UI Events<br />
<span class="small">The definition of 'FocusEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-focusevent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'FocusEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

9

Yes

Yes

Yes

Yes

24

Yes

Yes

Yes

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

`relatedTarget`

Yes

12

48

9

Yes

Yes

Yes

Yes

48

Yes

Yes

Yes

## See also

- The [`Event`](event) base interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent</a>

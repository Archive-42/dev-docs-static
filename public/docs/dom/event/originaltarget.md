# Event.originalTarget

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The original target of the event before any retargetings. (Mozilla-specific)

In presence of [XBL](https://developer.mozilla.org/en-US/docs/XBL) anonymous content this will be the anonymous node the event originally fired on. See [Anonymous Content\#Event_Flow_and_Targeting](https://developer.mozilla.org/en-US/docs/XBL/XBL_1.0_Reference/Anonymous_Content#Event_Flow_and_Targeting) for more details.

Note: `originalTarget` may also be native anonymous content (see [bug 208427](https://bugzilla.mozilla.org/show_bug.cgi?id=208427)), in which case it's useless for non-privileged code.

See also [Comparison of Event Targets](comparison_of_event_targets)

## Example

_Need an example that makes sense here_

## Specifications

This is a Mozilla-specific property. Defined in `/dom/public/idl/events/nsIDOMNSEvent.idl`

This event property is **not defined** in the [W3.org DOM Level 2 Events](https://www.w3.org/TR/DOM-Level-2-Events/events.html)

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

`originalTarget`

No

No

Yes

No

No

No

No

No

Yes

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/originalTarget" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/originalTarget</a>

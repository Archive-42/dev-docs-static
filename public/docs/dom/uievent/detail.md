UIEvent.detail
==============

The `UIEvent.detail` read-only property, when non-zero, provides the current (or next, depending on the event) click count.

For `click` or `dblclick` events, `UIEvent.detail` is the current click count.

For `mousedown` or `mouseup` events, `UIEvent.detail` is *1 plus* the current click count.

For all other [`UIEvent`](../uievent) objects, `UIEvent.detail` is always zero.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-UIEvent-detail">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'UIEvent.detail' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-UIEvent-detail">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'UIEvent.detail' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`detail`

Yes

12

Yes

9

Always `0` on `click` and `dblclick` events. On `mousedown` and `mouseup` events, the count is not unique to the element, but is rather the global click count for the current document -- even across refreshes.

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/detail" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/detail</a>

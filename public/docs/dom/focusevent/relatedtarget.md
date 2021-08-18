# FocusEvent.relatedTarget

The `FocusEvent.relatedTarget` read-only property is the secondary target, depending on the type of event:

<table><thead><tr class="header"><th>Event name</th><th><code>target</code></th><th><code>relatedTarget</code></th></tr></thead><tbody><tr class="odd"><td><code>blur</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> losing focus</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> receiving focus (if any).</td></tr><tr class="even"><td><code>focus</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> receiving focus</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> losing focus (if any)</td></tr><tr class="odd"><td><code>focusin</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> receiving focus</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> losing focus (if any)</td></tr><tr class="even"><td><code>focusout</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> losing focus</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> receiving focus (if any)</td></tr></tbody></table>

Note that [many elements can't have focus](https://stackoverflow.com/a/42764495/1026), which is a common reason for `relatedTarget` to be `null`. `relatedTarget` may also be set to `null` for security reasons, like when tabbing in or out of a page.

[`MouseEvent.relatedTarget`](../mouseevent/relatedtarget) is a similar property for mouse events.

## Syntax

    secondTarget = focusEvent.relatedTarget

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#idl-focusevent">UI Events<br />
<span class="small">The definition of 'FocusEvent.relatedTarget' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-FocusEvent-relatedTarget">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'FocusEvent.relatedTarget' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

- The [`FocusEvent`](../focusevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent/relatedTarget" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FocusEvent/relatedTarget</a>

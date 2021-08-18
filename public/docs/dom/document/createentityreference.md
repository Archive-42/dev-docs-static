# Document.createEntityReference()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Prior to Gecko 7.0 this method showed up as present, due to bug [bug 9850](https://bugzilla.mozilla.org/show_bug.cgi?id=9850), it always only returned null. The only workaround is to create a text node, CDATA section, attribute node value, etc. which has the value referred to by the entity, using [Unicode escape sequences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#unicode_escape_sequences) or [fromCharCode()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode) as necessary.

## Specifications

[createEntityReference](https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-392B75AE)

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

`createEntityReference`

1-29

No

1-7

No

15-16

1-10

1-≤37

18-29

4-7

14-16

1-10

1.0-2.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createEntityReference" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createEntityReference</a>

Selection.focusOffset
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.focusOffset` read-only property returns the number of characters that the selection's focus is offset within the [`Selection.focusNode`](focusnode).

This number is zero-based. If the selection ends with the first character in the [`Selection.focusNode`](focusnode), `0` is returned.

Syntax
------

    offset = sel.focusOffset

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-focusoffset">Selection API<br />
<span class="small">The definition of 'Selection.focusOffset' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`focusOffset`

1

12

1

9

≤12.1

1.3

1

18

4

≤12.1

1

1.0

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/focusOffset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/focusOffset</a>

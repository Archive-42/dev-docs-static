Selection.anchorOffset
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.anchorOffset` read-only property returns the number of characters that the selection's anchor is offset within the [`Selection.anchorNode`](anchornode).

This number is zero-based. If the selection begins with the first character in the [`Selection.anchorNode`](anchornode), `0` is returned.

Syntax
------

    number = sel.anchorOffset

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-anchoroffset">Selection API<br />
<span class="small">The definition of 'Selection.anchorOffset' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`anchorOffset`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/anchorOffset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/anchorOffset</a>

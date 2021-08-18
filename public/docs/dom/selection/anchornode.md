Selection.anchorNode
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.anchorNode` read-only property returns the [`Node`](../node) in which the selection begins.

A user may make a selection from left to right (in document order) or right to left (reverse of document order). The anchor is where the user began the selection. This can be visualized by holding the Shift key and pressing the arrow keys on your keyboard. The selection's anchor does not move, but the selection's focus, the other end of the selection, does move.

Syntax
------

    node = sel.anchorNode

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-anchornode">Selection API<br />
<span class="small">The definition of 'Selection.anchorNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`anchorNode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/anchorNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/anchorNode</a>

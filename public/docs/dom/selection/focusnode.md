Selection.focusNode
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.focusNode` read-only property returns the [`Node`](../node) in which the selection ends.

A user may make a selection from left to right (in document order) or right to left (reverse of document order). The focus is where the user ended the selection. This can be visualized by holding the Shift key and pressing the arrow keys on your keyboard to modify the current selection. The selection's focus moves, but the selection's anchor, the other end of the selection, does not move.

Syntax
------

    node = sel.focusNode

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-focusnode">Selection API<br />
<span class="small">The definition of 'Selection.focusNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`focusNode`

1

12

1

9

≤12.1

5.1

1

18

4

≤12.1

Yes

1.0

See also
--------

-   [`Selection`](../selection), the interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/focusNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/focusNode</a>

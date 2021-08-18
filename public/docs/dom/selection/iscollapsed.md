Selection.isCollapsed
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Selection.isCollapsed` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which indicates whether or not there is currently any text selected. No text is selected when the selection's start and end points are at the same position in the content.

Keep in mind that a collapsed selection may still have one (or more, in Gecko) [`Range`](../range)s, so [`Selection.rangeCount`](rangecount) may not be zero. In that scenario, calling a [`Selection`](../selection) object's [`getRangeAt()`](getrangeat) method may return a `Range` object which is collapsed.

Syntax
------

    bool = sel.isCollapsed

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-selection-iscollapsed">Selection API<br />
<span class="small">The definition of 'Selection.isCollapsed' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Current</td></tr></tbody></table>

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

`isCollapsed`

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

-   [`Selection`](../selection)
-   [`Range`](../range)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Selection/isCollapsed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Selection/isCollapsed</a>

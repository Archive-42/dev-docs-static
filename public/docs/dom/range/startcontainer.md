Range.startContainer
====================

The `Range.startContainer` read-only property returns the [`Node`](../node) within which the `Range` starts. To change the start position of a node, use one of the [`Range.setStart()`](setstart) methods.

Syntax
------

    startRangeNode = range.startContainer;

Example
-------

    range = document.createRange();
    range.setStart(startNode,startOffset);
    range.setEnd(endNode,endOffset);
    startRangeNode = range.startContainer;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-startcontainer">DOM<br />
<span class="small">The definition of 'Range.endContainer' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level-2-Range-attr-startParent">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.startContainer' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`startContainer`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/startContainer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/startContainer</a>

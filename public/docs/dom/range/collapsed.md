Range.collapsed
===============

The `Range.collapsed` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating whether the start and end points of the [`Range`](../range) are at the same position. It returns `true` if the start and end boundary points of the [`Range`](../range) are the same point in the DOM, `false` if not.

A collapsed [`Range`](../range) is empty (containing no content), and specifies a single point in a DOM tree. To collapse a range, see the [`Range.collapse()`](collapse) method.

Syntax
------

    isCollapsed = range.collapsed;

Example
-------

    let range = document.createRange();

    range.setStart(startNode, startOffset);
    range.setEnd(endNode, endOffset);
    isCollapsed = range.collapsed;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-collapsed">DOM<br />
<span class="small">The definition of 'Range.collapsed' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level-2-Range-attr-collapsed">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.collapsed' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`collapsed`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/collapsed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/collapsed</a>

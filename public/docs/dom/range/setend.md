Range.setEnd()
==============

The `Range.setEnd()` method sets the end position of a [`Range`](../range) to be located at the given offset into the specified node x.Setting the end point above (higher in the document) than the start point will result in a collapsed range with the start and end points both set to the specified end position.

Syntax
------

    range.setEnd(endNode, endOffset);

### Parameters

`endNode`  
The [`Node`](../node) inside which the [`Range`](../range) should end.

`endOffset`  
An integer greater than or equal to zero representing the offset for the end of the `Range` from the start of `endNode`.

### Return value

`undefined`.

### Exceptions

Exceptions are thrown as [`DOMException`](../domexception) objects of the following types:

`InvalidNodeTypeError`  
The node specified by `endNode` is a doctype node; range endpoints cannot be located inside a doctype node.

`IndexSizeError`  
The value specified by `endOffset` is either greater than or equal to the length of the node or is less than zero.

Usage notes
-----------

If the `endNode` is a [`Node`](../node) of type [`Text`](../text), [`Comment`](../comment), or [`CDataSection`](../cdatasection), then `endOffset` is the number of characters from the start of `endNode`. For other [`Node`](../node) types, `endOffset` is the number of child nodes between the start of the `endNode`.

Example
-------

    const range = document.createRange();
    const endNode = document.getElementsByTagName('p').item(3);
    const endOffset = endNode.childNodes.length;
    range.setEnd(endNode, endOffset);

`setEnd()` is commonly used in conjunction with [`setStart()`](setstart) to fully configure a range.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-setend">DOM<br />
<span class="small">The definition of 'Range.setEnd()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-setEnd">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.setEnd()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`setEnd`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/setEnd" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/setEnd</a>

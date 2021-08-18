Range.surroundContents()
========================

The `Range.surroundContents()` method moves content of the [`Range`](../range) into a new node, placing the new node at the start of the specified range.

This method is nearly equivalent to `newNode.appendChild(range.extractContents()); range.insertNode(newNode)`. After surrounding, the boundary points of the `range` include `newNode`.

An exception will be thrown, however, if the [`Range`](../range) splits a non-[`Text`](../text) node with only one of its boundary points. That is, unlike the alternative above, if there are partially selected nodes, they will not be cloned and instead the operation will fail.

Syntax
------

    range.surroundContents(newParent);

### Parameters

`newParent`  
A [`Node`](../node) with which to surround the contents.

Example
-------

### HTML

    <span class="header-text">Put this in a headline</span>

### JavaScript

    const range = document.createRange();
    const newParent = document.createElement('h1');

    range.selectNode(document.querySelector('.header-text'));
    range.surroundContents(newParent);

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-surroundcontents">DOM<br />
<span class="small">The definition of 'Range.surroundContents()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-surroundContents">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.surroundContents()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`surroundContents`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/surroundContents" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/surroundContents</a>

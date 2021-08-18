TreeWalker.currentNode
======================

The `TreeWalker.currentNode` property represents the [`Node`](../node) on which the [`TreeWalker`](../treewalker) is currently pointing at.

Syntax
------

    node = treeWalker.currentNode;
    treeWalker.currentNode = node;

Example
-------

    var treeWalker = document.createTreeWalker(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    root = treeWalker.currentNode; // the root element as it is the first element!

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-treewalker-currentnode">DOM<br />
<span class="small">The definition of 'TreeWalker.currrentNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/">Document Object Model (DOM) Level 2 Traversal and Range Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-TreeWalker-currentNode">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'TreeWalker.currentNode' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`currentNode`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

See also
--------

-   The [`TreeWalker`](../treewalker) interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/currentNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/currentNode</a>

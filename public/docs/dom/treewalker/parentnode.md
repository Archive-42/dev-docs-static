TreeWalker.parentNode()
=======================

The `TreeWalker.parentNode()` method moves the current [`Node`](../node) to the first *visible* ancestor node in the document order, and returns the found node. If no such node exists, or if it is above the `TreeWalker`'s *root node*, returns `null` and the current node is not changed.

Syntax
------

    node = treeWalker.parentNode();

Example
-------

    var treeWalker = document.createTreeWalker(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    var node = treeWalker.parentNode(); // returns null as there is no parent

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-treewalker-parentnode">DOM<br />
<span class="small">The definition of 'TreeWalker.parentNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/">Document Object Model (DOM) Level 2 Traversal and Range Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-TreeWalker-parentNode">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'TreeWalker.parentNode' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`parentNode`

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

-   The [`TreeWalker`](../treewalker) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/parentNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/parentNode</a>

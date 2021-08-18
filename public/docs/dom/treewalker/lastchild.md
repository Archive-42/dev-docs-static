TreeWalker.lastChild()
======================

The `TreeWalker.lastChild()` method moves the current [`Node`](../node) to the last *visible* child of the current node, and returns the found child. It also moves the current node to this child. If no such child exists, returns `null` and the current node is not changed.

Syntax
------

    node = treeWalker.lastChild();

Example
-------

    var treeWalker = document.createTreeWalker(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    var node = treeWalker.lastChild(); // returns the last visible child of the root element

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-treewalker-lastchild">DOM<br />
<span class="small">The definition of 'TreeWalker.lastChild' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/">Document Object Model (DOM) Level 2 Traversal and Range Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-TreeWalker-lastChild">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'TreeWalker.lastChild' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`lastChild`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/lastChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/lastChild</a>

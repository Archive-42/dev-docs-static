TreeWalker.nextSibling()
========================

The `TreeWalker.nextSibling()` method moves the current [`Node`](../node) to its next sibling, if any, and returns the found sibling. If there is no such node, return `null` and the current node is not changed.

Syntax
------

    node = treeWalker.nextSibling();

Example
-------

    var treeWalker = document.createTreeWalker(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    treeWalker.firstChild();
    var node = treeWalker.nextSibling(); // returns null if the first child of the root element has no sibling

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-treewalker-nextsibling">DOM<br />
<span class="small">The definition of 'TreeWalker.nextSibling' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/">Document Object Model (DOM) Level 2 Traversal and Range Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-TreeWalker-nextSibling">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'TreeWalker.nextSibling' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`nextSibling`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/nextSibling" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/nextSibling</a>

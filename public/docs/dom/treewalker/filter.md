TreeWalker.filter
=================

The `TreeWalker.filter` read-only property returns a [`NodeFilter`](../nodefilter) that is the filtering object associated with the [`TreeWalker`](../treewalker).

When creating the `TreeWalker`, the filter object is passed in as the third parameter, and its method [`NodeFilter.acceptNode()`](../nodefilter/acceptnode) is called on every single node to determine whether or not to accept it.

Syntax
------

    nodeFilter = treeWalker.filter;

Example
-------

    var treeWalker = document.createTreeWalker(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    nodeFilter = treeWalker.filter; // document.body in this case

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-treewalker-filter">DOM<br />
<span class="small">The definition of 'TreeWalker.filter' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/">Document Object Model (DOM) Level 2 Traversal and Range Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-TreeWalker-filter">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'TreeWalker.filter' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`filter`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/filter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/filter</a>

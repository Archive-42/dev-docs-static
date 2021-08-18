NodeIterator.filter
===================

The `NodeIterator.filter` read-only method returns a [`NodeFilter`](../nodefilter) object, that is an object implement an `acceptNode(node)` method, used to screen nodes.

When creating the [`NodeIterator`](../nodeiterator), the filter object is passed in as the third parameter, and the object method `acceptNode(node)` is called on every single node to determine whether or not to accept it. This function should return the constant `NodeFilter.FILTER_ACCEPT` for cases when the node should be accepted and `NodeFilter.FILTER_REJECT` for cases when the node should be rejected.

Syntax
------

    nodeFilter = nodeIterator.filter;

Example
-------

    const nodeIterator = document.createNodeIterator(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    nodeFilter = nodeIterator.filter;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nodeiterator-filter">DOM<br />
<span class="small">The definition of 'NodeIterator.filter' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/">Document Object Model (DOM) Level 2 Traversal and Range Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-NodeIterator-filter">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'NodeIterator.filter' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

3.5

9

9

3

1

18

4

10.1

3

1.0

See also
--------

-   The interface this property belongs to: [`NodeIterator`](../nodeiterator).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/filter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/filter</a>

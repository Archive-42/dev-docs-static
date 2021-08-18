NodeIterator.root
=================

The `NodeIterator.root` read-only property represents the [`Node`](../node) that is the root of what the [`NodeIterator`](../nodeiterator) traverses.

Syntax
------

    root = nodeIterator.root;

Example
-------

    var nodeIterator = document.createNodeIterator(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    root = nodeIterator.root; // document.body in this case

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nodeiterator-root">DOM<br />
<span class="small">The definition of 'NodeIterator.root' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/">Document Object Model (DOM) Level 2 Traversal and Range Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-NodeIterator-root">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'NodeIterator.root' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`root`

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

-   The interface it belongs to: [`NodeIterator`](../nodeiterator).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/root" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/root</a>

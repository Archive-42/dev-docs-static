NodeIterator.nextNode()
=======================

The `NodeIterator.nextNode()` method returns the next node in the set represented by the [`NodeIterator`](../nodeiterator) and advances the position of the iterator within the set. The first call to `nextNode()` returns the first node in the set.

This method returns `null` when there are no nodes left in the set.

In old browsers, as specified in old versions of the specifications, the method may throws the `INVALID_STATE_ERR` [`DOMException`](../domexception) if this method is called after the [`NodeIterator.detach()`](detach)method. Recent browsers never throw.

Syntax
------

    node = nodeIterator.nextNode();

Example
-------

    var nodeIterator = document.createNodeIterator(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false // this optional argument is not used any more
    );
    currentNode = nodeIterator.nextNode(); // returns the next node

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nodeiterator-nextnode">DOM<br />
<span class="small">The definition of 'NodeIterator.nextNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>As <code>detach()</code> is now a no-op method, this method cannot throw anymore.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-NodeIterator-nextNode">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'NodeIterator.nextNode' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`nextNode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/nextNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/nextNode</a>

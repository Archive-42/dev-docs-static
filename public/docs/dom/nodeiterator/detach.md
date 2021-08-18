NodeIterator.detach()
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `NodeIterator.detach()` method is a no-op, kept for backward compatibility only.

Originally, it detached the [`NodeIterator`](../nodeiterator) from the set over which it iterates, releasing any resources used by the set and setting the iterator's state to `INVALID`. Once this method had been called, calls to other methods on `NodeIterator` would raise the `INVALID_STATE_ERR` exception.

Syntax
------

    nodeIterator.detach();

Example
-------

    var nodeIterator = document.createNodeIterator(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    nodeIterator.detach(); // detaches the iterator

    nodeIterator.nextNode(); // throws an INVALID_STATE_ERR exception

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nodeiterator-detach">DOM<br />
<span class="small">The definition of 'NodeIterator.detach' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Transformed in a no-op</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-NodeIterator-detach">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'NodeIterator.detach' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`detach`

1

12

3.5-22

9

9

3

1

18

4-22

10.1

3

1.0

See also
--------

-   The interface it belongs to: [`NodeIterator`](../nodeiterator).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/detach" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/detach</a>

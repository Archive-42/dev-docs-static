# NodeIterator.previousNode()

The `NodeIterator.previousNode()` method returns the previous node in the set represented by the [`NodeIterator`](../nodeiterator) and moves the position of the iterator backwards within the set.

This method returns `null` when the current node is the first node in the set.

In old browsers, as specified in old versions of the specifications, the method may throws the `INVALID_STATE_ERR` [`DOMException`](../domexception) if this method is called after the [`NodeIterator.detach()`](detach)method. Recent browsers never throw.

## Syntax

    node = nodeIterator.previousNode();

## Example

    var nodeIterator = document.createNodeIterator(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false // this optional argument is not used any more
    );
    currentNode = nodeIterator.nextNode(); // returns the next node
    previousNode = nodeIterator.previousNode(); // same result, since we backtracked to the previous node

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nodeiterator-previousnode">DOM<br />
<span class="small">The definition of 'NodeIterator.previousNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>As <code>detach()</code> is now a no-op method, this method cannot throw anymore.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-NodeIterator-previousNode">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'NodeIterator.previousNode' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`previousNode`

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

## See also

- The interface it belongs to: [`NodeIterator`](../nodeiterator).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/previousNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/previousNode</a>

# Node.parentNode

The `Node.parentNode` read-only property returns the parent of the specified node in the DOM tree.

## Syntax

    parentNode = node.parentNode

`parentNode` is the parent of the current node. The parent of an element is an `Element` node, a `Document` node, or a `DocumentFragment` node.

## Example

    if (node.parentNode) {
      // remove a node from the tree, unless
      // it's not in the tree already
      node.parentNode.removeChild(node);
    }

## Notes

`Document` and `DocumentFragment` [nodes](nodetype) can never have a parent, so `parentNode` will always return `null`.

It also returns `null` if the node has just been created and is not yet attached to the tree.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-parentnode">DOM<br />
<span class="small">The definition of 'Node: parentNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`parentNode`

1

12

1

5.5

7

1.1

1

18

4

10.1

1

1.0

## See also

- [`Node.firstChild`](firstchild)
- [`Node.lastChild`](lastchild)
- [`Node.childNodes`](childnodes)
- [`Node.nextSibling`](nextsibling)
- [`Node.parentElement`](parentelement)
- [`Node.previousSibling`](previoussibling)
- [`Node.removeChild`](removechild)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode</a>

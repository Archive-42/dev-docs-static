# Node.contains()

The `Node.contains()` method returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether a node is a descendant of a given node, i.e. the node itself, one of its direct children ([`childNodes`](childnodes)), one of the children's direct children, and so on.

## Syntax

    node.contains( otherNode )

## Example

This function checks to see if an element is in the page's body. As `contains` is inclusive and determining if the body contains itself isn't the intention of `isInPage` this case explicitly returns `false`.

    function isInPage(node) {
      return (node === document.body) ? false : document.body.contains(node);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-contains">DOM<br />
<span class="small">The definition of 'Node.contains()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`contains`

16

12

9

9

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Node` objects.

7

1.1

≤37

18

9

10.1

1

1.0

## See also

- [`Node.compareDocumentPosition`](comparedocumentposition)
- [`Node.hasChildNodes`](haschildnodes)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/contains" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/contains</a>

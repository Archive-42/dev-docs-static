# Node.ownerDocument

The `ownerDocument` read-only property of the [`Node`](../node) interface returns the top-level document object of the node.

## Syntax

    var document = element.ownerDocument;

### Value

`document` is the top-level [`Document`](../document) object in which all the child nodes are created. If this property is used on a node that is itself a document, the value is `null`.

## Example

    // Given a node "p", get the top-level HTML
    // child of the document object

    var d = p.ownerDocument;
    var html = d.documentElement;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-ownerdocument">DOM<br />
<span class="small">The definition of 'Node: ownerDocument' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`ownerDocument`

1

12

9

1-9

The `ownerDocument` of doctype nodes (that is, nodes for which `Node.nodeType` is `Node.DOCUMENT_TYPE_NODE` or 10) is `null`.

6

≤12.1

7

1

18

9

4-9

The `ownerDocument` of doctype nodes (that is, nodes for which `Node.nodeType` is `Node.DOCUMENT_TYPE_NODE` or 10) is `null`.

≤12.1

7

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/ownerDocument" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/ownerDocument</a>

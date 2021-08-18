# Document.adoptNode()

`Document.adoptNode()` transfers a [node](https://developer.mozilla.org/en-US/docs/Glossary/Node/DOM) from another [document](../document) into the method's document. The adopted node and its subtree is removed from its original document (if any), and its [`ownerDocument`](../node/ownerdocument) is changed to the current document. The node can then be inserted into the current document.

## Syntax

    const importedNode = document.adoptNode(externalNode);

### Parameters

`externalNode`  
The node from another document to be adopted.

### Return value

The copied `importedNode` in the scope of the importing document.

After calling this method, `importedNode` and `externalNode` are the same object.

**Note:** `importedNode`'s [`Node.parentNode`](../node/parentnode) is `null`, since it has not yet been inserted into the document tree!

## Example

    const iframe = document.querySelector('iframe');
    const iframeImages = iframe.contentDocument.querySelectorAll('img');
    const newParent = document.getElementById('images');

    iframeImages.forEach(function(imgEl) {
      newParent.appendChild(document.adoptNode(imgEl));
    });

## Notes

Before they can be inserted into the current document, nodes from external documents should either be:

- cloned using [`document.importNode()`](importnode); or
- adopted using [`document.adoptNode()`](adoptnode).

**Best Practice:** Although Firefox doesn't currently enforce this rule, we encourage you to follow this rule for improved future compatibility.

For more on the [`Node.ownerDocument`](../node/ownerdocument) issues, see the W3C DOM FAQ.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-adoptnode">DOM<br />
<span class="small">The definition of 'document.adoptNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`adoptNode`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

## See also

- [`document.importNode()`](importnode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/adoptNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/adoptNode</a>

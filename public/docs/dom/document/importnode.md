# Document.importNode()

The [`Document`](../document) object's `importNode()` method creates a copy of a [`Node`](../node) or [`DocumentFragment`](../documentfragment) from another document, to be inserted into the current document later.

The imported node is not yet included in the document tree. To include it, you need to call an insertion method such as [`appendChild()`](../node/appendchild) or [`insertBefore()`](../node/insertbefore) with a node that _is_ currently in the document tree.

Unlike [`document.adoptNode()`](adoptnode), the original node is not removed from its original document. The imported node is a clone of the original.

## Syntax

    const importedNode = document.importNode(externalNode [, deep]);

### Parameters

`externalNode`  
The external [`Node`](../node) or [`DocumentFragment`](../documentfragment) to import into the current document.

`deep` <span class="badge inline optional">Optional</span>  
A Boolean which controls whether to include the entire DOM subtree of the `externalNode` in the import.

- If `deep` is set to `true`, then `externalNode` and all of its descendants are copied.
- If `deep` is set to `false`, then only `externalNode` is imported — the new node has no children.

**Note:** In the DOM4 specification, `deep` was an optional argument with a default value of `true`.

**This default has changed in the latest spec!** The new default value is `false`.

**Best Practice:** Though it's still an optional argument, you should always provide the `deep` argument for backward _and_ forward compatibility.

- With Gecko 28.0 (Firefox 28 / Thunderbird 28 / SeaMonkey 2.25 / Firefox OS 1.3), the console warns developers not to omit the argument.
- Starting with Gecko 29.0 (Firefox 29 / Thunderbird 29 / SeaMonkey 2.26)), a shallow clone is defaulted instead of a deep clone.

### Return value

The copied `importedNode` in the scope of the importing document.

**Note:** `importedNode`'s [`Node.parentNode`](../node/parentnode) is `null`, since it has not yet been inserted into the document tree!

## Example

    const iframe  = document.querySelector("iframe");
    const oldNode = iframe.contentWindow.document.getElementById("myNode");
    const newNode = document.importNode(oldNode, true);
    document.getElementById("container").appendChild(newNode);

## Notes

Before they can be inserted into the current document, nodes from external documents should either be:

- cloned using [`document.importNode()`](importnode); or
- adopted using [`document.adoptNode()`](adoptnode).

**Best Practice:** Although Firefox doesn't currently enforce this rule, we encourage you to follow this rule for improved future compatibility.

For more on the [`Node.ownerDocument`](../node/ownerdocument) issues, see the W3C DOM FAQ.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-importnode">DOM<br />
<span class="small">The definition of 'document.importNode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#Core-Document-importNode">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'document.importNode()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`importNode`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`deep_optional`

Yes

≤18

10

No

Yes

Yes

Yes

Yes

10

Yes

Yes

Yes

## See also

- [`document.adoptNode()`](adoptnode), which behaves very similar to this method
- [`Node.appendChild()`](../node/appendchild)
- [`Node.insertBefore()`](../node/insertbefore)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/importNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/importNode</a>

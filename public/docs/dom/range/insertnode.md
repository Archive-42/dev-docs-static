# Range.insertNode()

The `Range.insertNode()` method inserts a node at the start of the [`Range`](../range).

The new node is inserted at the start boundary point of the `Range`. If the new node is to be added to a text [`Node`](../node), that `Node` is split at the insertion point, and the insertion occurs between the two text nodes.

If the new node is a document fragment, the children of the document fragment are inserted instead.

## Syntax

    range.insertNode(newNode);

### Parameters

_newNode_  
The [`Node`](../node) to insert at the start of the `range`.

## Example

    range = document.createRange();
    newNode = document.createElement("p");
    newNode.appendChild(document.createTextNode("New Node Inserted Here"));
    range.selectNode(document.getElementsByTagName("div").item(0));
    range.insertNode(newNode);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-insertnode">DOM<br />
<span class="small">The definition of 'Range.insertNode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-insertNode">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.insertNode()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`insertNode`

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

`collapsed_ranges`

Yes

12

14

9

9

Yes

Yes

Yes

14

10.1

Yes

Yes

## See also

- [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/insertNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/insertNode</a>

# Range.endOffset

The `Range.endOffset` read-only property returns a number representing where in the [`Range.endContainer`](endcontainer) the [`Range`](../range) ends.

If the `endContainer` is a [`Node`](../node) of type [`Text`](../text), [`Comment`](../comment), or [`CDATASection`](../cdatasection), then the offset is the number of characters from the start of the `endContainer` to the boundary point of the [`Range`](../range). For other [`Node`](../node) types, the `endOffset` is the number of child nodes between the start of the `endContainer` and the boundary point of the [`Range`](../range). This property is read-only. To change the `endOffset` of a [`Range`](../range), use one of the [`Range.setEnd`](setend) methods.

## Syntax

    endRangeOffset = range.endOffset;

## Example

    var range = document.createRange();

    range.setStart(startNode,startOffset);
    range.setEnd(endNode,endOffset);
    endRangeOffset = range.endOffset;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-endoffset">DOM<br />
<span class="small">The definition of 'Range.endOffset' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level-2-Range-attr-endOffset">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.endOffset' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`endOffset`

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

## See also

- [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/endOffset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/endOffset</a>

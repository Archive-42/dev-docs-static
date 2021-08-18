# Range.selectNode()

The `Range.selectNode()` method sets the [`Range`](../range) to contain the [`Node`](../node) and its contents. The parent [`Node`](../node) of the start and end of the [`Range`](../range) will be the same as the parent of the _referenceNode_.

## Syntax

    range.selectNode(referenceNode);

### Parameters

_referenceNode_  
The [`Node`](../node) to select within a [`Range`](../range).

## Example

    let range = document.createRange();
    let referenceNode = document.getElementsByTagName('div').item(0);

    range.selectNode(referenceNode);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-selectnode">DOM<br />
<span class="small">The definition of 'Range.selectNode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-selectNode">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.selectNode()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`selectNode`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/selectNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/selectNode</a>

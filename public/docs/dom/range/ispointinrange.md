# Range.isPointInRange()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Range.isPointInRange()` method returns a boolean indicating whether the given point is in the [`Range`](../range). It returns `true` if the point (cursor position) at `offset` within `ReferenceNode` is within this range.

## Syntax

    bool = range.isPointInRange( referenceNode, offset )

### Parameters

_referenceNode_  
The [`Node`](../node) to compare with the [`Range`](../range).

_offset_  
The offset into [`Node`](../node) of the point to compare with the [`Range`](../range).

## Example

    range = document.createRange();
    range.selectNode(document.getElementsByTagName("div").item(0));
    bool = range.isPointInRange(document.getElementsByTagName("p").item(0),1);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-ispointinrange">DOM<br />
<span class="small">The definition of 'Range.isPointInRange()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`isPointInRange`

1

15

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

## See also

- [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/isPointInRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/isPointInRange</a>

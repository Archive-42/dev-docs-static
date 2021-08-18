# Range.comparePoint()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Range.comparePoint()` method returns `-1`, `0`, or `1` depending on whether the `referenceNode` is before, the same as, or after the [`Range`](../range).

If the _reference node_ is a [`Node`](../node) of type [`Text`](../text), [`Comment`](../comment), or [`CDATASection`](../cdatasection), then offset is the number of characters from the start of _reference node_. For other [`Node`](../node) types, offset is the number of child nodes between the start of the _reference node_.

## Syntax

    returnValue = range.comparePoint(referenceNode, offset)

### Parameters

`referenceNode`  
The [`Node`](../node) to compare with the [`Range`](../range).

`offset`  
An integer greater than or equal to zero representing the offset inside the _referenceNode_.

## Example

    range = document.createRange();
    range.selectNode(document.getElementsByTagName('div').item(0));
    returnValue = range.comparePoint(document.getElementsByTagName('p').item(0), 1);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-comparepoint">DOM<br />
<span class="small">The definition of 'Range.comparePoint()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial specification.</td></tr></tbody></table>

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

`comparePoint`

1

17

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/comparePoint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/comparePoint</a>

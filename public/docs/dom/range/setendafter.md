# Range.setEndAfter()

The `Range.setEndAfter()` method sets the end position of a [`Range`](../range) relative to another [`Node`](../node). The parent `Node` of end of the `Range` will be the same as that for the `referenceNode`.

## Syntax

    range.setEndAfter(referenceNode);

### Parameters

`referenceNode`  
The [`Node`](../node) to end the [`Range`](../range) after.

## Example

    var range = document.createRange();
    var referenceNode = document.getElementsByTagName('div').item(0);

    range.setEndAfter(referenceNode);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-setendafter">DOM<br />
<span class="small">The definition of 'Range.setEndAfter()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-setEndAfter">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.setEndAfter()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`setEndAfter`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/setEndAfter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/setEndAfter</a>

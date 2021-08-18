# Range.setStartAfter()

The `Range.setStartAfter()` method sets the start position of a [`Range`](../range) relative to a [`Node`](../node). The parent [`Node`](../node) of the start of the [`Range`](../range) will be the same as that for the `referenceNode`.

## Syntax

    range.setStartAfter(referenceNode);

### Parameters

_referenceNode_  
The [`Node`](../node) to start the [`Range`](../range) after.

## Example

    var range = document.createRange();
    var referenceNode = document.getElementsByTagName("div").item(0);

    range.setStartAfter(referenceNode);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-setstartafter">DOM<br />
<span class="small">The definition of 'Range.setStartAfter()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-setStartAfter">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.setStartAfter()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`setStartAfter`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/setStartAfter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/setStartAfter</a>

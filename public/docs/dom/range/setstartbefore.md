# Range.setStartBefore()

The `Range.setStartBefore()` method sets the start position of a [`Range`](../range) relative to another [`Node`](../node). The parent [`Node`](../node) of the start of the [`Range`](../range) will be the same as that for the `referenceNode`.

## Syntax

    range.setStartBefore(referenceNode);

### Parameters

_referenceNode_  
The [`Node`](../node) before which the [`Range`](../range) should start.

## Example

    var range = document.createRange();
    var referenceNode = document.getElementsByTagName("div").item(0);

    range.setStartBefore(referenceNode);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-setstartbefore">DOM<br />
<span class="small">The definition of 'Range.setStartBefore()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-setStartBefore">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.setStartBefore()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`setStartBefore`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/setStartBefore" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/setStartBefore</a>

# Range.compareBoundaryPoints()

The `Range.compareBoundaryPoints()` method compares the boundary points of the [`Range`](../range) with those of another range.

## Syntax

    compare = range.compareBoundaryPoints(how, sourceRange);

### Return value

`compare`  
A number, `-1`, `0`, or `1`, indicating whether the corresponding boundary-point of the [`Range`](../range) is respectively before, equal to, or after the corresponding boundary-point of _sourceRange_.

### Parameters

`how`  
A constant describing the comparison method:

- `Range.END_TO_END` compares the end boundary-point of _sourceRange_ to the end boundary-point of `Range`.
- `Range.END_TO_START` compares the end boundary-point of _sourceRange_ to the start boundary-point of `Range`.
- `Range.START_TO_END` compares the start boundary-point of _sourceRange_ to the end boundary-point of `Range`.
- `Range.START_TO_START` compares the start boundary-point of _sourceRange_ to the start boundary-point of `Range`.

If the value of the parameter is invalid, a [`DOMException`](../domexception) with a `NotSupportedError` code is thrown.

`sourceRange`  
A [`Range`](../range) to compare boundary points with the range.

## Example

    var range, sourceRange, compare;
    range = document.createRange();
    range.selectNode(document.getElementsByTagName("div")[0]);
    sourceRange = document.createRange();
    sourceRange.selectNode(document.getElementsByTagName("div")[1]);
    compare = range.compareBoundaryPoints(Range.START_TO_END, sourceRange);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-compareboundarypoints">DOM<br />
<span class="small">The definition of 'Range.compareBoundaryPoints()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-compareBoundaryPoints">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.compareBoundaryPoints()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`compareBoundaryPoints`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/compareBoundaryPoints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/compareBoundaryPoints</a>

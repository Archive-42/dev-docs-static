# Document.createRange()

The `Document.createRange()` method returns a new [`Range`](../range) object.

## Syntax

    range = document.createRange();

range is the created [`Range`](../range) object.

## Example

    let range = document.createRange();

    range.setStart(startNode, startOffset);
    range.setEnd(endNode, endOffset);

## Notes

Once a `Range` is created, you need to set its boundary points before you can make use of most of its methods.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createrange">DOM<br />
<span class="small">The definition of 'document.createRange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createRange`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createRange</a>

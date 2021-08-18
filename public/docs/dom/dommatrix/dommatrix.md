# DOMMatrix()

The `DOMMatrix` constructor creates a new [`DOMMatrix`](../dommatrix) object which represents 4x4 matrices, suitable for 2D and 3D operations..

## Syntax

    var domMatrix = new DOMMatrix([init])

### Parameters

init <span class="badge inline optional">Optional</span>  
A string containing a sequence of numbers or an array of numbers specifying the matrix you want to create, or a CSS transform string.

## Example

This example creates a DOMMatrix to use as an argument for calling <span class="page-not-created">`Point.matrixTransform()`</span>.

    var point = new DOMPoint(5, 4);
    var scaleX = 2;
    var scaleY = 3;
    var translateX = 12;
    var translateY = 8;
    var angle = Math.PI / 2;
    var matrix = new DOMMatrix([
      Math.sin(angle) * scaleX,
      Math.cos(angle) * scaleX,
      -Math.sin(angle) * scaleY,
      Math.cos(angle) * scaleY,
      translateX,
      translateY
    ]);
    var transformedPoint = point.matrixTransform(matrix);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dommatrixreadonly-dommatrixreadonly">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMMatrix' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`DOMMatrix`

61

79

33

No

48

11

61

61

33

45

11

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrix/DOMMatrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrix/DOMMatrix</a>

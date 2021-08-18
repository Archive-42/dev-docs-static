# DOMPointReadOnly()

The `DOMPointReadOnly()` constructor returns a new [`DOMPointReadOnly`](../dompointreadonly) object representing a point in 2D or 3D space, optionally with perspective, whose values cannot be altered by script code.

## Syntax

    point = new DOMPointReadOnly(x, y, z, w);

### Parameters

`x` <span class="badge inline optional">Optional</span>  
The value of the horizontal coordinate, x, as a floating point number. The default value is 0.

`y` <span class="badge inline optional">Optional</span>  
The value of the vertical coordinate, y, as a floating point number. The default value is 0.

`z` <span class="badge inline optional">Optional</span>  
The value of the depth coordinate, z, as a floating point number. The default value is 0.

`w` <span class="badge inline optional">Optional</span>  
The value of the perspective, w, as a floating point number. The default is 1.

**Note:** Each of these values is what's called an _unrestricted_ number. In addition to any finite floating-point value, you may use special values such as ±[`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity) and [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN).

### Return value

A new [`DOMPointReadOnly`](../dompointreadonly) object representing the specified location in space.

## Examples

The following code demonstrates creating both 2D and 3D points.

    var point2D = new DOMPointReadOnly(50, 25);
    var point3D = new DOMPointReadOnly(50, 0, 10);
    var perspectivePoint3D = new DOMPointReadOnly(50, 50, 25, 0.5);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dompointreadonly">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMPointReadOnly' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`DOMPointReadOnly`

61

79

62

No

48

10.1

61

61

62

45

10.3

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/DOMPointReadOnly" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/DOMPointReadOnly</a>

# DOMPointInit.x

The **[`DOMPointInit`](../dompointinit)** dictionary's `x` property is used to specify the x component of a point in 2D or 3D space when either creating or serializing a [`DOMPoint`](../dompoint) or [`DOMPointReadOnly`](../dompointreadonly).

In general, positive values `x` mean to the right, and negative values of `x` means to the left, assuming that transforms have not altered the orientation of the axes.

## Syntax

    var DOMPointInit = {
      x: xPos
    };

    DOMPointInit.x = xPos;

    var xPos = DOMPointInit.x;

### Value

A double-precision floating-point value indicating the point's x coordinate. This value is **unrestricted**, meaning that it is allowed to be infinite or invalid (that is, its value may be [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) or [`±Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)).

If this property is missing when the `DOMPointInit` object is passed into `fromPoint()`, the value is assumed to be 0 by default.

`DOMPointInit` is used as an input when calling either [`DOMPointReadOnly.fromPoint()`](../dompointreadonly/frompoint) or [`DOMPoint.fromPoint()`](../dompoint/frompoint), and is returned by the [`DOMPointReadOnly.toJSON()`](../dompointreadonly/tojson) and [`DOMPointReadOnly.toJSON`](../dompointreadonly/tojson) methods.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompointinit-x">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'x' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`x`

?

?

62

No

?

No

?

?

62

?

No

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit/x" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit/x</a>

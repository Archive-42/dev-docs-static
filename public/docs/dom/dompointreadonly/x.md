# DOMPointReadOnly.x

The `DOMPointReadOnly` interface's `x` property holds the horizontal coordinate, x, for a read-only point in space. This property cannot be changed by JavaScript code in this read-only version of the `DOMPoint` object.

In general, positive values `x` mean to the right, and negative values of `x` means to the left, assuming no transforms have resulted in a reversal.

## Syntax

    const xPos = someDOMPointReadOnly.x;

### Value

A double-precision floating-point value indicating the x coordinate's value for the point. This value is **unrestricted**, meaning that it is allowed to be infinite or invalid (that is, its value may be [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) or [`±Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompointreadonly-x">Geometry Interfaces Module Level 1<br />
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

61

79

31

No

48

10.1

61

61

31

45

10.3

8.0

## See also

- The other coordinate properties: [`y`](y), [`z`](z), and the perspective value, [`w`](w).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/x" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/x</a>

# DOMPointReadOnly.z

The `DOMPointReadOnly` interface's `z` property holds the depth coordinate, z, for a read-only point in space. If your script needs to be able to change the value of this property, you should instead use the [`DOMPoint`](../dompoint) object.

In general, positive values of `z` mean toward the user (out from the screen), and negative values of `z` mean away from the user (into the screen), assuming no transforms have resulted in a reversal.

## Syntax

    const zPos = someDOMPointReadOnly.z;

### Value

A double-precision floating-point value indicating the z coordinate's value for the point. This value is **unrestricted**, meaning that it is allowed to be infinite or invalid (that is, its value may be [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) or [`±Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompointreadonly-z">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'z' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`z`

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

- The other coordinate properties: [`x`](x), [`y`](y), and the perspective value, [`w`](w).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/z" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/z</a>

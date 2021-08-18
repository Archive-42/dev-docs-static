# DOMPointReadOnly.w

The `DOMPointReadOnly` interface's `w` property holds the point's perspective value, `w`, for a read-only point in space. If your script needs to be able to change the value of this property, you should instead use the [`DOMPoint`](../dompoint) object.

## Syntax

    const perspective = someDOMPointReadOnly.w

### Value

A double-precision floating-point value indicating the `w` perspective value for the point. This value is **unrestricted**, meaning that it is allowed to be infinite or invalid (that is, its value may be [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) or [`±Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)). The default is `1.0`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompointreadonly-w">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'w' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`w`

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

- The other coordinate properties: [`x`](x), [`y`](y), and [`z`](z).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/w" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointReadOnly/w</a>

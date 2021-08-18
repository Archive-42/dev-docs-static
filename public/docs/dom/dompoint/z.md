# DOMPoint.z

The `DOMPoint` interface's `z` property specifies the depth coordinate of a point in space. Unless transforms have changed the orientation, a `z` of 0 is the plane of the screen, with positive values extending outward toward the user from the screen, and negative values receding into the distance behind the screen.

## Syntax

    var zPos = DOMPoint.z;

### Value

A double-precision floating-point value indicating the _z_ coordinate's value for the point. This value is **unrestricted**, meaning that it is allowed to be infinite or invalid (that is, its value may be [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) or [`±Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompoint-z">Geometry Interfaces Module Level 1<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/z" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPoint/z</a>

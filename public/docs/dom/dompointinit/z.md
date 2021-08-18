# DOMPointInit.z

The **[`DOMPointInit`](../dompointinit)** dictionary's `z` property is used to specify the _z_-coordinate of a point in 2D or 3D space when either creating or serializing to JSON a [`DOMPoint`](../dompoint) or [`DOMPointReadOnly`](../dompointreadonly) object.

Typically, a `z` value of 0 represents the plane of the screen. As the value increases, the point moves outward from the screen toward the user. As the value decreases, the point moves farther from the user, with negative values being behind the screen, receding into the distance.

Of course, if [transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transforms) have been applied, the axes may have changed orientation.

## Syntax

    var DOMPointInit = {
      z: zPos
    };

    DOMPointInit.z = zPos;

    var zPos = DOMPointInit.z;

### Value

A double-precision floating-point value indicating the point's _z_-coordinate. This value is **unrestricted**, meaning that it is allowed to be infinite or invalid (that is, its value may be [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) or [`±Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)).

There are two methods which use `DOMPointInit`:

- The static function [`DOMPointReadOnly.fromPoint()`](../dompointreadonly/frompoint) takes an object that complies with `DOMPointInit` as its sole input parameter, to specify the coordinates and perspective value of the new point to be created. This method is, by inheritance, also available as [`DOMPoint.fromPoint()`](../dompoint/frompoint).
- The [`DOMPointReadOnly.toJSON()`](../dompointreadonly/tojson) method returns a `DOMPointInit` object that describes the same point as the original point. By inheritance, this method is also available as [`DOMPointReadOnly.toJSON`](../dompointreadonly/tojson).

If this property is missing when the `DOMPointInit` object is passed into `fromPoint()`, the value is assumed to be 0 by default.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompointinit-z">Geometry Interfaces Module Level 1<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit/z" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit/z</a>

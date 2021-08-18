# DOMPointInit.w

The **[`DOMPointInit`](../dompointinit)** dictionary's `w` property is used to specify the _w_ perspective value of a point in space when either creating or serializing to JSON a [`DOMPoint`](../dompoint) or [`DOMPointReadOnly`](../dompointreadonly) object.

## Syntax

    var DOMPointInit = {
      w: wPerspective
    };

    DOMPointInit.w = wPerspective;

    var wPerspective = DOMPointInit.w;

### Value

A double-precision floating-point value indicating the point's _w_ perspective value. This value is **unrestricted**, meaning that it is allowed to be infinite or invalid (that is, its value may be [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) or [`±Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)).

There are two methods which use `DOMPointInit`:

- The static function [`DOMPointReadOnly.fromPoint()`](../dompointreadonly/frompoint) takes an object that complies with `DOMPointInit` as its sole input parameter, to specify the coordinates and perspective value of the new point to be created. This method is, by inheritance, also available as [`DOMPoint.fromPoint()`](../dompoint/frompoint).
- The [`DOMPointReadOnly.toJSON()`](../dompointreadonly/tojson) method returns a `DOMPointInit` object that describes the same point as the original point. By inheritance, this method is also available as [`DOMPointReadOnly.toJSON`](../dompointreadonly/tojson).

This value is assumed to be 1 by default if not included in the `DOMPointInit` object passed into `fromPoint()`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompointinit-w">Geometry Interfaces Module Level 1<br />
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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit/w" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit/w</a>

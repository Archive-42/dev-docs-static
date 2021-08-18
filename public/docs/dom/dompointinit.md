# DOMPointInit

The `DOMPointInit` dictionary is used to provide the values of the coordinates and perspective when creating and JSONifying a [`DOMPoint`](dompoint) or [`DOMPointReadOnly`](dompointreadonly) object.

It's used as an input parameter to the `DOMPoint`/`DOMPointReadOnly` method [`fromPoint()`](dompointreadonly/frompoint). It's used as the return value when calling [`toJSON()`](dompointreadonly/tojson).

## Properties

[`DOMPointInit.x`](dompointinit/x)  
An unrestricted floating-point value indicating the `x`-coordinate of the point in space. This is generally the horizontal coordinate, with positive values being to the right and negative values to the left. The default value is `0`.

[`DOMPointInit.y`](dompointinit/y)  
An unrestricted floating-point number providing the point's `y`-coordinate. This is the vertical coordinate, and barring any transforms applied to the coordinate system, positive values are downward and negative values upward toward the top of the screen. The default is `0`.

[`DOMPointInit.z`](dompointinit/z)  
An unrestricted floating-point value which gives the point's `z`-coordinate, which is (assuming no transformations that alter the situation) the depth coordinate; positive values are closer to the user and negative values retreat back into the screen. The default value is `0`.

[`DOMPointInit.w`](dompointinit/w)  
The point's `w` perspective value, given as an unrestricted floating-point number. The default is `1`.

## Example

This example creates a new `DOMPoint` representing the top-left corner of the current window, with a `z` component added to move the point closer to the user. This same code will work to create a `DOMPointReadOnly` object; just change the interface name in the code.

    const pointDesc = {
      x: window.screenX,
      y: window.screenY,
      z: 5.0
    };

    const windTopLeft = DOMPoint.fromPoint(pointDesc)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dom-dompointreadonly-frompoint">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMPointReadOnly.fromPoint()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`DOMPointInit`

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

`y`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMPointInit</a>

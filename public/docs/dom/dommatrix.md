# DOMMatrix (WebKitCSSMatrix)

The `DOMMatrix` interface represents 4×4 matrices, suitable for 2D and 3D operations including rotation and translation. It is a mutable version of the [`DOMMatrixReadOnly`](dommatrixreadonly) interface.

`WebKitCSSMatrix` is an alias to `DOMMatrix`.

This interface should be available inside [web workers](web_workers_api), though some implementations don't allow it yet.

## Constructor

[`DOMMatrix()`](dommatrix/dommatrix)  
Creates and returns a new `DOMMatrix` object.

## Properties

_This interface inherits properties from [`DOMMatrixReadOnly`](dommatrixreadonly), though some of these properties are altered to be mutable._

`is2D` <span class="badge inline readonly">Read only </span>  
A Boolean flag whose value is `true` if the matrix was initialized as a 2D matrix. If `false`, the matrix is 3D.

`isIdentity` <span class="badge inline readonly">Read only </span>  
A Boolean whose value is `true` if the matrix is the [identity matrix](https://en.wikipedia.org/wiki/Identity_matrix). The identity matrix is one in which every value is `0` _except_ those on the main diagonal from top-left to bottom-right corner (in other words, where the offsets in each direction are equal).

`m11`, `m12`, `m13`, `m14`, `m21`, `m22`, `m23`, `m24`, `m31`, `m32`, `m33`, `m34`, `m41`, `m42`, `m43`, `m44`  
Double-precision floating-point values representing each component of a 4×4 matrix, where `m11` through `m14` are the first column, `m21` through `m24` are the second column, and so forth.

`a`, `b`, `c`, `d`, `e`, `f`  
Double-precision floating-point values representing the components of a 4×4 matrix which are required in order to perform 2D rotations and translations. These are aliases for specific components of a 4×4 matrix, as shown below.

<table><thead><tr class="header"><th><code>2D</code></th><th><code>3D equivalent</code></th></tr></thead><tbody><tr class="odd"><td><code>a</code></td><td><code>m11</code></td></tr><tr class="even"><td><code>b</code></td><td><code>m12</code></td></tr><tr class="odd"><td><code>c</code></td><td><code>m21</code></td></tr><tr class="even"><td><code>d</code></td><td><code>m22</code></td></tr><tr class="odd"><td><code>e</code></td><td><code>m41</code></td></tr><tr class="even"><td><code>f</code></td><td><code>m42</code></td></tr></tbody></table>

## Methods

_This interface includes the following methods, as well as the methods it inherits from [`DOMMatrixReadOnly`](dommatrixreadonly)._

<span class="page-not-created">`DOMMatrix.invertSelf()`</span>  
Modifies the matrix by inverting it. If the matrix can't be inverted, its components are all set to `NaN`, and <span class="page-not-created">`is2D`</span> returns `false`.

<span class="page-not-created">`DOMMatrix.multiplySelf()`</span>  
Modifies the matrix by post-multiplying it with the specified `DOMMatrix`. This is equivalent to the dot product `A⋅B`, where matrix `A` is the source matrix and `B` is the matrix given as an input to the method. Returns itself.

<span class="page-not-created">`DOMMatrix.preMultiplySelf()`</span>  
Modifies the matrix by pre-multiplying it with the specified `DOMMatrix`. This is equivalent to the dot product `B⋅A`, where matrix `A` is the source matrix and `B` is the matrix given as an input to the method. Returns itself.

<span class="page-not-created">`DOMMatrix.translateSelf()`</span>  
Modifies the matrix by applying the specified vector. The default vector is `[0, 0, 0]`. Returns itself.

<span class="page-not-created">`DOMMatrix.scaleNonUniformSelf()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Modifies the matrix by applying the specified scaling on the X, Y, and Z axes, centered at the given origin. By default, the Y and Z axes' scaling factors are both `1`, but the scaling factor for X must be specified. The default origin is `(0, 0, 0)`. Returns itself.

<span class="page-not-created">`DOMMatrix.scaleSelf()`</span>  
Modifies the matrix by applying the specified scaling factors, with the center located at the specified origin. Also returns itself. By default, the scaling factor is `1` for all three axes, and the origin is `(0, 0, 0)`. Returns itself.

<span class="page-not-created">`DOMMatrix.scale3dSelf()`</span>  
Modifies the matrix by applying the specified scaling factor to all three axes, centered on the given origin. Returns itself.

<span class="page-not-created">`DOMMatrix.rotateSelf()`</span>  
Modifies the matrix by rotating itself around each axis by the specified number of degrees. Returns itself.

<span class="page-not-created">`DOMMatrix.rotateAxisAngleSelf()`</span>  
Modifies the matrix by rotating it by the specified angle around the given vector. Returns itself.

<span class="page-not-created">`DOMMatrix.rotateFromVectorSelf()`</span>  
Modifies the matrix by rotating it by the angle between the specified vector and `(1, 0)`. Returns itself.

<span class="page-not-created">`DOMMatrix.setMatrixValue()`</span>  
Replaces the contents of the matrix with the matrix described by the specified transform or transforms. Returns itself.

<span class="page-not-created">`DOMMatrix.skewXSelf()`</span>  
Modifies the matrix by applying the specified skew transformation along the X-axis. Returns itself.

<span class="page-not-created">`DOMMatrix.skewYSelf()`</span>  
Modifies the matrix by applying the specified skew transformation along the Y-axis. Returns itself.

## Static methods

_This interface inherits methods from [`DOMMatrixReadOnly`](dommatrixreadonly)._

<span class="page-not-created">`fromFloat32Array()`</span>  
Creates a new mutable `DOMMatrix` object given an array of single-precision (32-bit) floating-point values. If the array has six values, the result is a 2D matrix; if the array has 16 values, the result is a 3D matrix. Otherwise, a `TypeError` exception is thrown.

<span class="page-not-created">`fromFloat64Array()`</span>  
Creates a new mutable `DOMMatrix` object given an array of double-precision (64-bit) floating-point values. If the array has six values, the result is a 2D matrix; if the array has 16 values, the result is a 3D matrix. Otherwise, a `TypeError` exception is thrown.

<span class="page-not-created">`fromMatrix()`</span>  
Creates a new mutable `DOMMatrix` object given an existing matrix or a <span class="page-not-created">`DOMMatrixInit`</span> dictionary which provides the values for its properties.

## Usage notes

The matrix defined by the `DOMMatrix` interface is comprised of four rows of four columns each. While it's beyond the scope of this article to explain the mathematics involved, this 4×4 size is enough to describe any transformation you might apply to either 2D or 3D geometries.

$$
\\begin{bmatrix}
m\_{11} & m\_{21} & m\_{31} & m\_{41} \\\\
m\_{12} & m\_{22} & m\_{32} & m\_{42} \\\\
m\_{13} & m\_{23} & m\_{33} & m\_{43} \\\\
m\_{14} & m\_{24} & m\_{34} & m\_{44} \\\\
\\end{bmatrix}
$$

**The positions of the 16 elements (m<sub>11</sub> through m<sub>44</sub>)** which comprise the 4×4 abstract matrix.

The `DOMMatrix` interface is designed with the intent that it will be used for all matrices within markup, supplanting the [`SVGMatrix`](svgmatrix) and [`CSSMatrix`](dommatrix) interfaces.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMMatrix">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMMatrix' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

?

12

12-79

?

11

10

?

Yes

?

?

?

?

Yes

?

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

`invertSelf`

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

`multiplySelf`

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

`preMultiplySelf`

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

`rotateAxisAngleSelf`

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

`rotateFromVectorSelf`

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

`rotateSelf`

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

`scale3dSelf`

61

79

33

Starting in Firefox 69, the first parameter (`scale`) is now optional with a default value of 1, per the specification. Previously it was required.

No

48

11

61

61

33

Firefox for Android requires the first parameter (`scale`).

45

11

8.0

`scaleSelf`

61

79

33

Firefox 69 introduced support for the modern six-parameter syntax for `scaleSelf()`. Previously, it only supported the older three-parameter syntax: `scale(scaleX[, originX][, originY]]])`.

No

48

11

61

61

33

Firefox for Android only supports the older three-parameter syntax for `scaleSelf()`: `scale(scaleX[, originX][, originY]]])`, and not the six-parameter syntax.

45

11

8.0

`setMatrixValue`

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

`skewXSelf`

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

`skewYSelf`

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

`translateSelf`

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

`worker_support`

61

79

69

No

48

11

61

61

No

45

11

8.0

BCD tables only load in the browser

BCD tables only load in the browser

## See also

- Its non-modifiable counterpart, [`DOMMatrixReadOnly`](dommatrixreadonly)
- [`SVGMatrix`](svgmatrix), the SVG matrix intended to be superseded by [`DOMMatrix`](dommatrix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrix</a>

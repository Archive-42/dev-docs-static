# DOMMatrixReadOnly

The `DOMMatrixReadOnly` interface represents a read-only 4×4 matrix, suitable for 2D and 3D operations. The [`DOMMatrix`](dommatrix) interrface—which is based upon `DOMMatrixReadOnly`—adds [mutability](https://en.wikipedia.org/wiki/Immutable_object), allowing you to alter the matrix after creating it. A 4×4 matrix is suitable to describe any rotation and translation in 3D.

This interface should be available inside [web workers](web_workers_api), though some implementations doesn't allow it yet.

## Properties

_This interface doesn't inherit any properties._

`is2D` <span class="badge inline readonly">Read only </span>  
A Boolean flag whose value is `true` if the matrix was initialized as a 2D matrix. If `false`, the matrix is 3D.

`isIdentity` <span class="badge inline readonly">Read only </span>  
A Boolean whose value is `true` if the matrix is the [identity matrix](https://en.wikipedia.org/wiki/Identity_matrix). The identity matrix is one in which every value is `0` _except_ those on the main diagonal from top-left to bottom-right corner (in other words, where the offsets in each direction are equal).

`m11`, `m12`, `m13`, `m14`, `m21`, `m22`, `m23`, `m24`, `m31`, `m32`, `m33`, `m34`, `m41`, `m42`, `m43`, `m44`  
Double-precision floating-point values representing each component of a 4×4 matrix, where `m11` through `m14` are the first column, `m21` through `m24` are the second column, and so forth.

`a`, `b`, `c`, `d`, `e`, `f`  
Double-precision floating-point values representing the components of a 4×4 matrix which are required in order to perform 2D rotations and translations. These are aliases for specific components of a 4×4 matrix, as shown below.

<table><thead><tr class="header"><th>2D</th><th>3D equivalent</th></tr></thead><tbody><tr class="odd"><td><code>a</code></td><td><code>m11</code></td></tr><tr class="even"><td><code>b</code></td><td><code>m12</code></td></tr><tr class="odd"><td><code>c</code></td><td><code>m21</code></td></tr><tr class="even"><td><code>d</code></td><td><code>m22</code></td></tr><tr class="odd"><td><code>e</code></td><td><code>m41</code></td></tr><tr class="even"><td><code>f</code></td><td><code>m42</code></td></tr></tbody></table>

## Methods

_This interface doesn't inherit any methods. None of the following methods alter the original matrix._

[`DOMMatrixReadOnly.flipX()`](dommatrixreadonly/flipx)  
Returns a new [`DOMMatrix`](dommatrix) created by flipping the source matrix around its X-axis. This is equivalent to multiplying the matrix by `DOMMatrix(-1, 0, 0, 1, 0, 0)`. The original matrix is not modified.

<span class="page-not-created">`DOMMatrixReadOnly.flipY()`</span>  
Returns a new [`DOMMatrix`](dommatrix) created by flipping the source matrix around its Y-axis. This is equivalent to multiplying the matrix by `DOMMatrix(1, 0, 0, -1, 0, 0)`. The original matrix is not modified.

<span class="page-not-created">`DOMMatrixReadOnly.inverse()`</span>  
Returns a new [`DOMMatrix`](dommatrix) created by inverting the source matrix. If the matrix cannot be inverted, the new matrix's components are all set to `NaN` and its `is2D` property is set to `false`. The original matrix is not altered.

<span class="page-not-created">`DOMMatrixReadOnly.multiply()`</span>  
Returns a new [`DOMMatrix`](dommatrix) created by computing the dot product of the source matrix and the specified matrix: `A⋅B`. If no matrix is specified as the multiplier, the matrix is multiplied by a matrix in which every element is `0` _except_ the bottom-right corner and the element immediately above and to its left: `m33` and `m34`. These have the default value of `1`. The original matrix is not modified.

<span class="page-not-created">`DOMMatrixReadOnly.rotateAxisAngle()`</span>  
Returns a new [`DOMMatrix`](dommatrix) created by rotating the source matrix by the given angle around the specified vector. The original matrix is not modified.

<span class="page-not-created">`DOMMatrixReadOnly.rotate()`</span>  
Returns a new [`DOMMatrix`](dommatrix) created by rotating the source matrix around each of its axes by the specified number of degrees. The original matrix is not altered.

<span class="page-not-created">`DOMMatrixReadOnly.rotateFromVector()`</span>  
Returns a new [`DOMMatrix`](dommatrix) created by rotating the source matrix by the angle between the specified vector and `(1, 0)`. The original matrix is not modified.

[`DOMMatrixReadOnly.scale()`](dommatrixreadonly/scale)  
Returns a new [`DOMMatrix`](dommatrix) created by scaling the source matrix by the amount specified for each axis, centered on the given origin. By default, the X and Z axes are scaled by `1` and the Y axis has no default scaling value. The default origin is `(0, 0, 0)`. The original matrix is not modified.

<span class="page-not-created">`DOMMatrixReadOnly.scale3d()`</span>  
Returns a new [`DOMMatrix`](dommatrix) created by scaling the source 3D matrix by the given factor along all its axes, centered on the specified origin point. The default origin is `(0, 0, 0)`. The original matrix is not modified.

<span class="page-not-created">`DOMMatrixReadOnly.scaleNonUniform()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns a new [`DOMMatrix`](dommatrix) created by applying the specified scaling on the X, Y, and Z axes, centered at the given origin. By default, the Y and Z axes' scaling factors are both `1`, but the scaling factor for X must be specified. The default origin is `(0, 0, 0)`. The original matrix is not changed.

<span class="page-not-created">`DOMMatrixReadOnly.skewX()`</span>  
Returns a new [`DOMMatrix`](dommatrix) created by applying the specified skew transformation to the source matrix along its X-axis. The original matrix is not modified.

<span class="page-not-created">`DOMMatrixReadOnly.skewY()`</span>  
Returns a new [`DOMMatrix`](dommatrix) created by applying the specified skew transformation to the source matrix along its Y-axis. The original matrix is not modified.

<span class="page-not-created">`DOMMatrixReadOnly.toFloat32Array()`</span>  
Returns a new [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing all 16 elements (`m11`, `m12`, `m13`, `m14`, `m21`, `m22`, `m23`, `m24`, `m31`, `m32`, `m33`, `m34`, `m41`, `m42`, `m43`, `m44`) which comprise the matrix. The elements are stored into the array as single-precision floating-point numbers in column-major (colexographical access, or "colex") order. (In other words, down the first column from top to bottom, then the second column, and so forth.)

<span class="page-not-created">`DOMMatrixReadOnly.toFloat64Array()`</span>  
Returns a new [`Float64Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float64Array) containing all 16 elements (`m11`, `m12`, `m13`, `m14`, `m21`, `m22`, `m23`, `m24`, `m31`, `m32`, `m33`, `m34`, `m41`, `m42`, `m43`, `m44`) which comprise the matrix. The elements are stored into the array as double-precision floating-point numbers in column-major (colexographical access access or "colex") order. (In other words, down the first column from top to bottom, then the second column, and so forth.)

<span class="page-not-created">`DOMMatrixReadOnly.toJSON()`</span>  
Returns a JSON representation of the `DOMMatrixReadOnly` object.

<span class="page-not-created">`DOMMatrixReadOnly.toString()`</span>  
Creates and returns a [`DOMString`](domstring) object which contains a string representation of the matrix in CSS matrix syntax, using the appropriate CSS matrix notation. See the <span class="page-not-created">`matrix()`</span> CSS function for details on this syntax.

For a 2D matrix, the elements `a` through `f` are listed, for a total of six values and the form `matrix(a, b, c, d, e, f)`.

For a 3D matrix, the returned string contains all 16 elements and takes the form `matrix3d(m11, m12, m13, m14, m21, m22, m23, m24, m31, m32, m33, m34, m41, m42, m43, m44)`. See the CSS <span class="page-not-created">`matrix3d()`</span> function for details on the 3D notation's syntax.

Throws an `InvalidStateError` exception if any of the elements in the matrix are non-finite (even if, in the case of a 2D matrix, the non-finite values are in elements not used by the 2D matrix representation).

<span class="page-not-created">`DOMMatrixReadOnly.transformPoint()`</span>  
Transforms the specified point using the matrix, returning a new [`DOMPoint`](dompoint) object containing the transformed point. Neither the matrix nor the original point are altered.

[`DOMMatrixReadOnly.translate()`](dommatrixreadonly/translate)  
Returns a new [`DOMMatrix`](dommatrix) containing a matrix calculated by translating the source matrix using the specified vector. By default, the vector is `(0, 0, 0)`. The original matrix is not changed.

## Static methods

_This interface inherits methods from [`DOMMatrixReadOnly`](dommatrixreadonly)._

<span class="page-not-created">`fromFloat32Array()`</span>  
Creates a new mutable `DOMMatrix` object given an array of single-precision (32-bit) floating-point values. If the array has six values, the result is a 2D matrix; if the array has 16 values, the result is a 3D matrix. Otherwise, a `TypeError` exception is thrown.

<span class="page-not-created">`fromFloat64Array()`</span>  
Creates a new mutable `DOMMatrix` object given an array of double-precision (64-bit) floating-point values. If the array has six values, the result is a 2D matrix; if the array has 16 values, the result is a 3D matrix. Otherwise, a `TypeError` exception is thrown.

<span class="page-not-created">`fromMatrix()`</span>  
Creates a new mutable `DOMMatrix` object given an existing matrix or a <span class="page-not-created">`DOMMatrixInit`</span> dictionary which provides the values for its properties. If no matrix is specified, the matrix is initialized with every element set to `0` _except_ the bottom-right corner and the element immediately above and to its left: `m33` and `m34`. These have the default value of `1`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#dommatrixreadonly">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMMatrixReadOnly' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`DOMMatrixReadOnly`

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

`DOMMatrixReadOnly`

61

79

62

No

48

11

61

61

62

45

11

8.0

`a`

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

`b`

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

`c`

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

`d`

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

`e`

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

`f`

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

`flipX`

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

`flipY`

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

`fromFloat32Array`

61

79

69

No

48

11

61

61

79

45

11

8.0

`fromFloat64Array`

61

79

69

No

48

11

61

61

79

45

11

8.0

`fromMatrix`

61

79

69

No

48

11

61

61

79

45

11

8.0

`inverse`

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

`is2D`

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

`isIdentity`

61

79

59

No

48

11

61

61

59

45

11

8.0

`m11`

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

`m12`

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

`m13`

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

`m14`

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

`m21`

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

`m22`

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

`m23`

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

`m24`

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

`m31`

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

`m32`

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

`m33`

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

`m34`

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

`m41`

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

`m42`

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

`m43`

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

`m44`

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

`multiply`

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

`rotate`

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

`rotateAxisAngle`

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

`rotateFromVector`

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

`scale`

61

79

33

Firefox 69 introduced support for the modern six-parameter syntax for `scale()`. Previously, it only supported the older three-parameter syntax: `scale(scaleX[, originX][, originY]]])`.

No

48

11

61

61

33

Firefox for Android 79 introduced support for the modern six-parameter syntax for `scale()`. Previously, it only supported the older three-parameter syntax: `scale(scaleX[, originX][, originY]]])`.

45

11

8.0

`scale3d`

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

Starting in Firefox for Android 79, the first parameter (`scale`) is now optional with a default value of 1, per the specification. Previously it was required.

45

11

8.0

`scaleNonUniform`

73

79

33

No

60

No

73

73

33

52

No

11.0

`scaleNonUniformSelf`

No

No

33-69

No

No

No

No

No

33-79

No

No

No

`skewX`

61

79

33

Prior to Firefox 69, the `sx` parameter was required; you may now call `skewX()` with no inputs. A value of 0 is correctly assumed.

No

48

11

61

61

33

Prior to Firefox for Android 79, the `sx` parameter was required; you may now call `skewX()` with no inputs. A value of 0 is correctly assumed.

45

11

8.0

`skewY`

61

79

33

Prior to Firefox 69, the `sy` parameter was required; you may now call `skewY()` with no inputs. A value of 0 is correctly assumed.

No

48

11

61

61

33

Prior to Firefox for Android 79, the `sy` parameter was required; you may now call `skewY()` with no inputs. A value of 0 is correctly assumed.

45

11

8.0

`toFloat32Array`

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

`toFloat64Array`

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

`toJSON`

61

79

62

No

48

11

61

61

62

45

11

8.0

`toString`

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

`transform`

61

79

33

Prior to Firefox 69, the `tx` and `ty` parameters were required; they are now correctly optional, each defaulting to a value of 0.

No

48

11

61

61

33

Prior to Firefox for Android 79, the `tx` and `ty` parameters were required; they are now correctly optional, each defaulting to a value of 0.

45

11

8.0

`transformPoint`

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

`translate`

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

79

45

11

8.0

## See also

- The mutable matrix type, [`DOMMatrix`](dommatrix), which is based on this one.
- [`SVGMatrix`](svgmatrix) and [`CSSMatrix`](dommatrix), the [SVG](https://developer.mozilla.org/en-US/docs/Glossary/SVG) and [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) specific types that should be getting replaced by this interface.
- The CSS [`matrix()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function#matrix()>) and [`matrix3d()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function#matrix3d()>) functional notation that can be generated from this interface to be used in a CSS [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrixReadOnly" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMMatrixReadOnly</a>

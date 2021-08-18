SVGMatrix
=========

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Many of SVG's graphics operations utilize 2x3 matrices of the form:

    [a c e]
    [b d f]

which, when expanded into a 3x3 matrix for the purposes of matrix arithmetic, become:

    [a c e]
    [b d f]
    [0 0 1]

An `SVGMatrix` object can be designated as read only, which means that attempts to modify the object will result in an exception being thrown.

**Warning:** SVG 2 replaced the `SVGMatrix` interface by the more general [`DOMMatrix`](dommatrix) and [`DOMMatrixReadOnly`](dommatrixreadonly) interfaces.

Properties
----------

<span class="page-not-created">`SVGMatrix.a`</span>  
A float representing the *a* component of the matrix.

<span class="page-not-created">`SVGMatrix.b`</span>  
A float representing the *b* component of the matrix.

<span class="page-not-created">`SVGMatrix.c`</span>  
A float representing the *c* component of the matrix.

<span class="page-not-created">`SVGMatrix.d`</span>  
A float representing the *d* component of the matrix.

<span class="page-not-created">`SVGMatrix.e`</span>  
A float representing the *e* component of the matrix.

<span class="page-not-created">`SVGMatrix.f`</span>  
A float representing the *f* component of the matrix.

Methods
-------

<span class="page-not-created">`SVGMatrix.multiply()`</span>  
Performs matrix multiplication. This matrix is post-multiplied by another matrix, returning the resulting new matrix as `SVGMatrix`.

<span class="page-not-created">`SVGMatrix.inverse()`</span>  
Returns the inverse matrix as `SVGMatrix`.

<span class="page-not-created">`SVGMatrix.translate()`</span>  
Post-multiplies a translation transformation on the current matrix and returns the resulting matrix as `SVGMatrix`.

<span class="page-not-created">`SVGMatrix.scale()`</span>  
Post-multiplies a uniform scale transformation on the current matrix and returns the resulting matrix as `SVGMatrix`.

<span class="page-not-created">`SVGMatrix.scaleNonUniform()`</span>  
Post-multiplies a non-uniform scale transformation on the current matrix and returns the resulting matrix as `SVGMatrix`.

<span class="page-not-created">`SVGMatrix.rotate()`</span>  
Post-multiplies a rotation transformation on the current matrix and returns the resulting matrix as `SVGMatrix`.

<span class="page-not-created">`SVGMatrix.rotateFromVector()`</span>  
Post-multiplies a rotation transformation on the current matrix and returns the resulting matrix as `SVGMatrix`. The rotation angle is determined by taking (+/-) atan(y/x). The direction of the vector (x, y) determines whether the positive or negative angle value is used.

<span class="page-not-created">`SVGMatrix.flipX()`</span>  
Post-multiplies the transformation \[-1 0 0 1 0 0\] and returns the resulting matrix as `SVGMatrix`.

<span class="page-not-created">`SVGMatrix.flipY()`</span>  
Post-multiplies the transformation \[1 0 0 -1 0 0\] and returns the resulting matrix as `SVGMatrix`.

<span class="page-not-created">`SVGMatrix.skewX()`</span>  
Post-multiplies a skewX transformation on the current matrix and returns the resulting matrix as `SVGMatrix`.

<span class="page-not-created">`SVGMatrix.skewY()`</span>  
Post-multiplies a skewY transformation on the current matrix and returns the resulting matrix as `SVGMatrix`.

Exceptions
----------

A [`DOMException`](domexception) with the code `NO_MODIFICATION_ALLOWED_ERR` is raised when attempting updating a read-only attribute or when the object itself is read-only.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/SVG11/coords.html#InterfaceSVGMatrix">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGMatrix' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`SVGMatrix`

5

12

1.5

9

≤12.1

5

≤37

18

4

≤12.1

4

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGMatrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGMatrix</a>

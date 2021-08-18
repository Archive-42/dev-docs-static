XRRigidTransform.matrix
=======================

The read-only [`XRRigidTransform`](../xrrigidtransform) property `matrix` returns the transform matrix represented by the object. The returned matrix can then be premultiplied with a column vector to rotate the vector by the 3D rotation specified by the [`orientation`](orientation), then translate it by the [`position`](position).

Syntax
------

    let matrix = xrRigidTransform.matrix;

### Value

A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing 16 entries which represents the 4x4 transform matrix which is described by the [`position`](position) and [`orientation`](orientation) properties.

Usage notes
-----------

### Matrix format

All 4x4 transform matrices used in WebGL are stored in 16-element [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array)s. The values are stored into the array in column-major order; that is, each column is written into the array top-down before moving to the right one column and writing the next column into the array. Thus, for an array \[a0, a1, a2, ..., a13, a14, a15\], the matrix looks like this:

$$\\begin{bmatrix}
{a\\lbrack 0\\rbrack} & {a\\lbrack 4\\rbrack} & {a\\lbrack 8\\rbrack} & {a\\lbrack 12\\rbrack} \\\\
{a\\lbrack 1\\rbrack} & {a\\lbrack 5\\rbrack} & {a\\lbrack 9\\rbrack} & {a\\lbrack 13\\rbrack} \\\\
{a\\lbrack 2\\rbrack} & {a\\lbrack 6\\rbrack} & {a\\lbrack 10\\rbrack} & {a\\lbrack 14\\rbrack} \\\\
{a\\lbrack 3\\rbrack} & {a\\lbrack 7\\rbrack} & {a\\lbrack 11\\rbrack} & {a\\lbrack 15\\rbrack} \\\\
\\end{bmatrix}$$

On the first request, the `matrix` gets computed. After that, it should be cached for performance reasons.

### Creating the matrix

In this section, intended for more advanced readers, we cover how the API calculates the matrix for the specified transform. It begins by allocating a new matrix and writing a 4x4 identity matrix into it:

$$\\begin{bmatrix}
1 & 0 & 0 & 0 \\\\
0 & 1 & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{bmatrix}$$

This is a transform that will not change either the orientation or position of any point, vector, or object to which it's applied.

Next, the `position` is placed into the right-hand column, like this, resulting in a translation matrix that will transform a coordinate system by the specified distance in each dimension, with no rotational change. Here `px`, `py`, and `pz` are the values of the `x`, `y`, and `z` members of the [`DOMPointReadOnly`](../dompointreadonly) `position`.

$$\\begin{bmatrix}
1 & 0 & 0 & p\_{x} \\\\
0 & 1 & 0 & p\_{y} \\\\
0 & 0 & 1 & p\_{z} \\\\
0 & 0 & 0 & 1 \\\\
\\end{bmatrix}$$

Then a rotation matrix is created by computing a column-vector rotation matrix from the unit quaternion specified by `orientation`:

$$\\begin{bmatrix}
{1 - 2(q\_{y}^{2} + q\_{z}^{2})} & {2(q\_{x}q\_{y} - q\_{z}q\_{w})} & {2(q\_{x}q\_{z} + q\_{y}q\_{w})} & 0 \\\\
{2(q\_{x}q\_{y} + q\_{z}q\_{w})} & {1 - 2(q\_{x}^{2} + q\_{z}^{2})} & {2(q\_{y}q\_{z} - q\_{x}q\_{w})} & 0 \\\\
{2(q\_{x}q\_{z} - q\_{y}q\_{w})} & {2(q\_{y}q\_{z} + q\_{x}q\_{w})} & {1 - 2(q\_{x}^{2} + q\_{y}^{2})} & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{bmatrix}$$

The final transform `matrix` is calculated by multiplying the translation matrix by the rotation matrix, in the order `(translation * rotation)`. This yields the final transform matrix as returned by `matrix`:

$$\\begin{bmatrix}
{1 - 2(q\_{y}^{2} + q\_{z}^{2})} & {2(q\_{x}q\_{y} - q\_{z}q\_{w})} & {2(q\_{x}q\_{z} + q\_{y}q\_{w})} & p\_{x} \\\\
{2(q\_{x}q\_{y} + q\_{z}q\_{w})} & {1 - 2(q\_{x}^{2} + q\_{z}^{2})} & {2(q\_{y}q\_{z} - q\_{x}q\_{w})} & p\_{y} \\\\
{2(q\_{x}q\_{z} - q\_{y}q\_{w})} & {2(q\_{y}q\_{z} + q\_{x}q\_{w})} & {1 - 2(q\_{x}^{2} + q\_{y}^{2})} & p\_{z} \\\\
0 & 0 & 0 & 1 \\\\
\\end{bmatrix}$$

Examples
--------

In this example, a transform is created to create a matrix which can be used as a transform during rendering of WebGL objects, in order to place objects to match a given offset and orientation. The `matrix` is then passed into a library function that uses WebGL to render an object matching a given name using the transform matrix specified to position and orient it.

    let transform = new XRRigidTransform(
                          {x: 0, y: 0.5, z: 0.5},
                          {x: 0, y: -0.5, z: -0.5, w: 1});
    drawGLObject("magic-lamp", transform.matrix);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrrigidtransform-matrix">WebXR Device API<br />
<span class="small">The definition of 'XRRigidTransform.matrix' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`matrix`

79

79

No

No

No

No

No

79

No

No

No

11.2

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/matrix" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRRigidTransform/matrix</a>

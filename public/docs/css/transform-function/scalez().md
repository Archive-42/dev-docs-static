# scaleZ()

The `scaleZ()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that resizes an element along the z-axis. Its result is a [`<transform-function>`](../transform-function) data type.

This scaling transformation modifies the z-coordinate of each element point by a constant factor, except when the scale factor is 1, in which case the function is the identity transform. The scaling is not isotropic, and the angles of the element are not conserved. `scaleZ(-1)` defines an [axial symmetry](https://en.wikipedia.org/wiki/Axial_symmetry), with the z-axis passing through the origin (as specified by the [`transform-origin`](../transform-origin) property).

In the above interactive examples, `perspective: 550px;` (to create a 3D space) and `transform-style: preserve-3d;` (so the children, the 6 sides of the cube, are also positioned in the 3D space), have been set on the cube.

**Note:** `scaleZ(sz)` is equivalent to `scale3d(1, 1, sz)`.

## Syntax

    scaleZ(s)

### Values

`s`  
Is a [`<number>`](../number) representing the scaling factor to apply on the z-coordinate of each point of the element.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

This transformation applies to the 3D space and can't be represented on the plane.

$\\begin{pmatrix}
1 & 0 & 0 \\\\
0 & 1 & 0 \\\\
0 & 0 & s \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & 0 & 0 \\\\
0 & 1 & 0 & 0 \\\\
0 & 0 & s & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

## Examples

### HTML

    <div>Normal</div>
    <div class="perspective">Translated</div>
    <div class="scaled-translated">Scaled</div>

### CSS

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .perspective {
      /* Includes a perspective to create a 3D space */
      transform: perspective(400px) translateZ(-100px);
      background-color: limegreen;
    }

    .scaled-translated {
      /* Includes a perspective to create a 3D space */
      transform: perspective(400px) scaleZ(2) translateZ(-100px);
      background-color: pink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#funcdef-scalez">CSS Transforms Level 2<br />
<span class="small">The definition of 'scaleZ()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scaleZ()`

1

12

3.5

\["Firefox 14 removed experimental support for [`skew()`](https://developer.mozilla.org/docs/Web/CSS/transform-function/skew), but it was reintroduced in Firefox 15.", "Before Firefox 16, the translation values of `matrix()` and `matrix3d()` could be [`<length>`](https://developer.mozilla.org/docs/Web/CSS/length)s, in addition to the standard [`<number>`](https://developer.mozilla.org/docs/Web/CSS/number)."\]

9

Internet Explorer 9 supports 2D but not 3D transforms. In version 9, mixing 2D and 3D transform functions invalidates the entire property.

10.5

3.1

2

18

4

11

3.2

1.0

`3d`

12

12

10

10

15

4

3

18

10

14

3.2

1.0

## See also

- `scaleX()`
- `scaleY()`
- [`transform`](../transform)
- [`<transform-function>`](../transform-function)
- [`transform-origin`](../transform-origin)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleZ()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleZ()</a>

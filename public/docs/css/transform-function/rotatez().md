# rotateZ()

The `rotateZ()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that rotates an element around the z-axis without deforming it. Its result is a [`<transform-function>`](../transform-function) data type.

The axis of rotation passes through an origin, defined by the [`transform-origin`](../transform-origin) CSS property.

**Note:** `rotateZ(a)` is equivalent to `rotate(a)` or `rotate3d(0, 0, 1, a)`.

**Note:** Unlike rotations in the 2D plane, the composition of 3D rotations is usually not commutative. In other words, the order in which the rotations are applied impacts the result.

## Syntax

The amount of rotation created by `rotateZ()` is specified by an [`<angle>`](../angle). If positive, the movement will be clockwise; if negative, it will be counter-clockwise.

    rotateZ(a)

### Values

`a`  
Is an [`<angle>`](../angle) representing the angle of the rotation. A positive angle denotes a clockwise rotation, a negative angle a counter-clockwise one.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

This transformation applies to the 3D space and can't be represented on the plane.

$\\begin{pmatrix}
{\\cos\\left( a \\right)} & {- \\sin\\left( a \\right)} & 0 \\\\
{\\sin\\left( a \\right)} & {\\cos\\left( a \\right)} & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
{\\cos\\left( a \\right)} & {- \\sin\\left( a \\right)} & 0 & 0 \\\\
{\\sin\\left( a \\right)} & {\\cos\\left( a \\right)} & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

## Examples

### HTML

    <div>Normal</div>
    <div class="rotated">Rotated</div>

### CSS

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .rotated {
      transform: rotateZ(45deg);
      background-color: pink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#funcdef-rotatez">CSS Transforms Level 2<br />
<span class="small">The definition of 'rotateZ()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`rotateZ()`

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

- [`transform`](../transform)
- [`<transform-function>`](../transform-function)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateZ()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateZ()</a>

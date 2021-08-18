# scaleY()

The `scaleY()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that resizes an element along the y-axis (vertically). Its result is a [`<transform-function>`](../transform-function) data type.

<img src="data:image/png;base64,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" width="365" height="381" />

It modifies the ordinate of each element point by a constant factor, except when the scale factor is 1, in which case the function is the identity transform. The scaling is not isotropic, and the angles of the element are not conserved. `scaleY(-1)` defines an [axial symmetry](https://en.wikipedia.org/wiki/Axial_symmetry), with a horizontal axis passing through the origin (as specified by the [`transform-origin`](../transform-origin) property).

**Note:** `scaleY(sy)` is equivalent to `scale(1, sy)` or `scale3d(1, sy, 1)`.

`transform: rotateX(180deg);` === `transform: scaleY(-1);`

## Syntax

    scaleY(s)

### Values

`s`  
Is a [`<number>`](../number) representing the scaling factor to apply on the ordinate of each point of the element.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

$\\begin{pmatrix}
1 & 0 \\\\
0 & s \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & 0 \\\\
0 & s & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & 0 \\\\
0 & s & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & 0 & 0 \\\\
0 & s & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[1 0 0 s 0 0]`

## Examples

### HTML

    <div>Normal</div>
    <div class="scaled">Scaled</div>

### CSS

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .scaled {
      transform: scaleY(0.6);
      background-color: pink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-scaley">CSS Transforms Level 1<br />
<span class="small">The definition of 'scaleY()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scaleY()`

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
- `scaleZ()`
- [`transform`](../transform)
- [`<transform-function>`](../transform-function)
- [`transform-origin`](../transform-origin)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleY()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleY()</a>

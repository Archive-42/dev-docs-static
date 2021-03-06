# scaleX()

The `scaleX()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that resizes an element along the x-axis (horizontally). Its result is a [`<transform-function>`](../transform-function) data type.

<img src="data:image/png;base64,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" width="372" height="315" />

It modifies the abscissa of each element point by a constant factor, except when the scale factor is 1, in which case the function is the identity transform. The scaling is not isotropic, and the angles of the element are not conserved. `scaleX(-1)` defines an [axial symmetry](https://en.wikipedia.org/wiki/Axial_symmetry), with a vertical axis passing through the origin (as specified by the [`transform-origin`](../transform-origin) property).

**Note:** `scaleX(sx)` is equivalent to `scale(sx, 1)` or `scale3d(sx, 1, 1)`.

## Syntax

    scaleX(s)

### Values

`s`  
Is a [`<number>`](../number) representing the scaling factor to apply on the abscissa of each point of the element.

Cartesian coordinates on ???<sup>2</sup>

Homogeneous coordinates on ??????<sup>2</sup>

Cartesian coordinates on ???<sup>3</sup>

Homogeneous coordinates on ??????<sup>3</sup>

$\\begin{pmatrix}
s & 0 \\\\
0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
s & 0 & 0 \\\\
0 & 1 & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
s & 0 & 0 \\\\
0 & 1 & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
s & 0 & 0 & 0 \\\\
0 & 1 & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[s 0 0 1 0 0]`

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
      transform: scaleX(0.6);
      background-color: pink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-scalex">CSS Transforms Level 1<br />
<span class="small">The definition of 'scaleX()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scaleX()`

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

- `scaleY()`
- `scaleZ()`
- [`transform`](../transform)
- [`<transform-function>`](../transform-function)
- [`transform-origin`](../transform-origin)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleX()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleX()</a>

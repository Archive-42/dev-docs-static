# skewX()

The `skewX()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that skews an element in the horizontal direction on the 2D plane. Its result is a [`<transform-function>`](../transform-function) data type.

This transformation is a shear mapping ([transvection](https://en.wikipedia.org/wiki/Shear_mapping)) that distorts each point within an element by a certain angle in the horizontal direction. The abscissa coordinate of each point is modified by a value proportionate to the specified angle and the distance to the origin; thus, the farther from the origin a point is, the greater will be the value added it.

**Note:** `skewX(a)` is equivalent to `skew(a)`.

## Syntax

    skewX(a)

### Values

`a`  
Is an [`<angle>`](../angle) representing the angle to use to distort the element along the abscissa.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

$\\begin{pmatrix}
1 & {\\tan\\left( a \\right)} \\\\
0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & {\\tan\\left( a \\right)} & 0 \\\\
0 & 1 & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & {\\tan\\left( a \\right)} & 0 \\\\
0 & 1 & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & {\\tan\\left( a \\right)} & 0 & 0 \\\\
0 & 1 & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[1 0 tan(a) 1 0 0]`

## Examples

### HTML

    <div>Normal</div>
    <div class="skewed">Skewed</div>

### CSS

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .skewed {
      transform: skewX(10deg); /* Equal to skew(10deg) */
      background-color: pink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-skewx">CSS Transforms Level 1<br />
<span class="small">The definition of 'skewX()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`skewX()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skewX()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skewX()</a>

# matrix()

The `matrix()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a homogeneous 2D transformation matrix. Its result is a [`<transform-function>`](../transform-function) data type.

**Note:** `matrix(a, b, c, d, tx, ty)` is a shorthand for `matrix3d(a, b, 0, 0, c, d, 0, 0, 0, 0, 1, 0, tx, ty, 0, 1)`.

## Syntax

The `matrix()` function is specified with six values. The constant values are implied and not passed as parameters; the other parameters are described in the column-major order.

**Note:** Until Firefox 16, Gecko accepted a [`<length>`](../length) value for tx and ty.

    matrix(a, b, c, d, tx, ty)

### Values

a b c d  
Are [`<number>`](../number)s describing the linear transformation.

tx ty  
Are [`<number>`](../number)s describing the translation to apply.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

$\\begin{pmatrix}
a & c \\\\
b & d \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
a & c & {tx} \\\\
b & d & {ty} \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
a & c & {tx} \\\\
b & d & {ty} \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
a & c & 0 & {tx} \\\\
b & d & 0 & {ty} \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[a b c d tx ty]`

The values represent the following functions:  
`matrix( scaleX(), skewY(), skewX(), scaleY(), translateX(), translateY() )`

## Examples

### HTML

    <div>Normal</div>
    <div class="changed">Changed</div>

### CSS

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .changed {
      transform: matrix(1, 2, -1, 1, 80, 80);
      background-color: pink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-matrix">CSS Transforms Level 1<br />
<span class="small">The definition of 'matrix()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`matrix()`

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
- `matrix3d()`
- [Understanding the CSS Transforms Matrix](https://dev.opera.com/articles/understanding-the-css-transforms-matrix/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/matrix()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/matrix()</a>

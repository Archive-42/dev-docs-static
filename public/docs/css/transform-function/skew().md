# skew()

The `skew()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that skews an element on the 2D plane. Its result is a [`<transform-function>`](../transform-function) data type.

This transformation is a shear mapping ([transvection](https://en.wikipedia.org/wiki/Shear_mapping)) that distorts each point within an element by a certain angle in the horizontal and vertical directions. The effect is as if you grabbed each corner of the element and pulled them along a certain angle.

The coordinates of each point are modified by a value proportionate to the specified angle and the distance to the origin. Thus, the farther from the origin a point is, the greater the value added to it.

## Syntax

The `skew()` function is specified with either one or two values, which represent the amount of skewing to be applied in each direction. If you only specify one value it is used for the x-axis and there will be no skewing on the y-axis.

    skew(ax)

    skew(ax, ay)

### Values

`ax`  
Is an [`<angle>`](../angle) representing the angle to use to distort the element along the x-axis (or abscissa).

`ay`  
Is an [`<angle>`](../angle) representing the angle to use to distort the element along the y-axis (or ordinate). If not defined, its default value is `0`, resulting in a purely horizontal skewing.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

$\\begin{pmatrix}
1 & {\\tan\\left( {ax} \\right)} \\\\
{\\tan\\left( {ay} \\right)} & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & {\\tan\\left( {ax} \\right)} & 0 \\\\
{\\tan\\left( {ay} \\right)} & 1 & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & {\\tan\\left( {ax} \\right)} & 0 \\\\
{\\tan\\left( {ay} \\right)} & 1 & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & {\\tan\\left( {ax} \\right)} & 0 & 0 \\\\
{\\tan\\left( {ay} \\right)} & 1 & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[1 tan(ay) tan(ax) 1 0 0]`

## Examples

### Skewing on the x-axis only

#### HTML

    <div>Normal</div>
    <div class="skewed">Skewed</div>

#### CSS

    body {
      margin: 20px;
    }

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .skewed {
      transform: skew(10deg); /* Equal to skewX(10deg) */
      background-color: pink;
    }

#### Result

### Skewing on both axes

#### HTML

    <div>Normal</div>
    <div class="skewed">Skewed</div>

#### CSS

    body {
      margin: 20px;
    }

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .skewed {
      transform: skew(10deg, 10deg);
      background-color: pink;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-skew">CSS Transforms Level 1<br />
<span class="small">The definition of 'skew()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`skew()`

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
- [skewX()](<skewx()>)
- [skewY()](<skewy()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skew()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skew()</a>

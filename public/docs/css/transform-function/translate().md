# translate()

The `translate()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) repositions an element in the horizontal and/or vertical directions. Its result is a [`<transform-function>`](../transform-function) data type.

<img src="data:image/png;base64,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" width="249" height="195" />

This transformation is characterized by a two-dimensional vector. Its coordinates define how much the element moves in each direction.

## Syntax

    /* Single <length-percentage> values */
    transform: translate(200px);
    transform: translate(50%);

    /* Double <length-percentage> values */
    transform: translate(100px, 200px);
    transform: translate(100px, 50%);
    transform: translate(30%, 200px);
    transform: translate(30%, 50%);

### Values

Single `<length-percentage>` values  
This value is a [`<length>`](../length) or [`<percentage>`](../percentage) representing the abscissa (horizontal, x-coordinate) of the translating vector. The ordinate (vertical, y-coordinate) of the translating vector will be set to `0`. For example, `translate(2px)` is equivalent to `translate(2px, 0)`. A percentage value refers to the width of the reference box defined by the [`transform-box`](../transform-box) property.

Double `<length-percentage>` values  
This value describes two [`<length>`](../length) or [`<percentage>`](../percentage) values representing both the abscissa (x-coordinate) and the ordinate (y-coordinate) of the translating vector. A percentage as first value refers to the width, as second part to the height of the reference box defined by the [`transform-box`](../transform-box) property.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

A translation is not a linear transformation in ℝ<sup>2</sup> and can't be represented using a Cartesian-coordinate matrix.

$\\begin{pmatrix}
1 & 0 & {tx} \\\\
0 & 1 & {ty} \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & {tx} \\\\
0 & 1 & {ty} \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & 0 & {tx} \\\\
0 & 1 & 0 & {ty} \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[1 0 0 1 tx ty]`

### Formal syntax

    translate(<length-percentage> , <length-percentage>?)

## Examples

### Using a single-axis translation

#### HTML

    <div>Static</div>
    <div class="moved">Moved</div>
    <div>Static</div>

#### CSS

    div {
      width: 60px;
      height: 60px;
      background-color: skyblue;
    }

    .moved {
      transform: translate(10px); /* Equal to: translateX(10px) or translate(10px, 0) */
      background-color: pink;
    }

#### Result

### Combining y-axis and x-axis translation

#### HTML

    <div>Static</div>
    <div class="moved">Moved</div>
    <div>Static</div>

#### CSS

    div {
      width: 60px;
      height: 60px;
      background-color: skyblue;
    }

    .moved {
      transform: translate(10px, 10px);
      background-color: pink;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-translate">CSS Transforms Level 1<br />
<span class="small">The definition of 'translate()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`translate()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate()</a>

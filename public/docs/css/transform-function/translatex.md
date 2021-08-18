# translateX()

The `translateX()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) repositions an element horizontally on the 2D plane. Its result is a [`<transform-function>`](../transform-function) data type.

<img src="data:image/png;base64,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" width="243" height="146" />

**Note:** `translateX(tx)` is equivalent to `translate(tx, 0)` or `translate3d(tx, 0, 0)`.

## Syntax

    /* <length-percentage> values */
    transform: translateX(200px);
    transform: translateX(50%);

### Values

`<length-percentage>`  
Is a [`<length>`](../length) or [`<percentage>`](../percentage) representing the abscissa of the translating vector. A percentage value refers to the width of the reference box defined by the [`transform-box`](../transform-box) property.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

A translation is not a linear transformation in ℝ<sup>2</sup> and can't be represented using a Cartesian-coordinate matrix.

$\\begin{pmatrix}
1 & 0 & t \\\\
0 & 1 & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & t \\\\
0 & 1 & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & 0 & t \\\\
0 & 1 & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[1 0 0 1 t 0]`

### Formal syntax

    translateX(<length-percentage>)

## Examples

### HTML

    <div>Static</div>
    <div class="moved">Moved</div>
    <div>Static</div>

### CSS

    div {
      width: 60px;
      height: 60px;
      background-color: skyblue;
    }

    .moved {
      transform: translateX(10px); /* Equal to translate(10px) */
      background-color: pink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-translatex">CSS Transforms Level 1<br />
<span class="small">The definition of 'translateX()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`translateX`

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

- [`translate`](../translate)
- <span class="page-not-created">`translatey`</span>
- [`transform`](../transform)
- [`<transform-function>`](../transform-function)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateX" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateX</a>

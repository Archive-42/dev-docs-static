# translateY()

The `translateY()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) repositions an element vertically on the 2D plane. Its result is a [`<transform-function>`](../transform-function) data type.

<img src="data:image/png;base64,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" width="243" height="195" />

**Note:** `translateY(ty)` is equivalent to `translate(0, ty)` or `translate3d(0, ty, 0)`.

## Syntax

    /* <length-percentage> values */
    transform: translateY(200px);
    transform: translateY(50%);

### Values

`<length-percentage>`  
The value is a [`<length>`](../length) or [`<percentage>`](../percentage) representing the ordinate of the translating vector. A percentage value refers to the height of the reference box defined by the [`transform-box`](../transform-box) property.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

A translation is not a linear transformation in ℝ<sup>2</sup> and can't be represented using a Cartesian-coordinate matrix.

$\\begin{pmatrix}
1 & 0 & 0 \\\\
0 & 1 & t \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & 0 \\\\
0 & 1 & t \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
1 & 0 & 0 & 0 \\\\
0 & 1 & 0 & t \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[1 0 0 1 0 t]`

### Formal syntax

    translateY(<length-percentage>)

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
      transform: translateY(10px);
      background-color: pink;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-translatey">CSS Transforms Level 1<br />
<span class="small">The definition of 'translateY()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`translateY()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateY()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateY()</a>

# translate3d()

The `translate3d()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) repositions an element in 3D space. Its result is a [`<transform-function>`](../transform-function) data type.

This transformation is characterized by a three-dimensional vector. Its coordinates define how much the element moves in each direction.

## Syntax

    translate3d(tx, ty, tz)

### Values

`tx`  
Is a [`<length>`](../length) or [`<percentage>`](../percentage) representing the abscissa of the translating vector.

`ty`  
Is a [`<length>`](../length) or [`<percentage>`](../percentage) representing the ordinate of the translating vector.

`tz`  
Is a [`<length>`](../length) representing the z component of the translating vector. It can't be a [`<percentage>`](../percentage) value; in that case the property containing the transform is considered invalid.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

This transformation applies to the 3D space and can't be represented on the plane.

A translation is not a linear transformation in ℝ<sup>3</sup> and can't be represented using a Cartesian-coordinate matrix.

$\\begin{pmatrix}
1 & 0 & 0 & {tx} \\\\
0 & 1 & 0 & {ty} \\\\
0 & 0 & 1 & {tz} \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

## Examples

### Using a single axis translation

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
      /* Equivalent to perspective(500px) translateX(10px) */
      transform: perspective(500px) translate3d(10px, 0, 0px);
      background-color: pink;
    }

#### Result

### Combining z-axis and x-axis translation

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
      transform: perspective(500px) translate3d(10px, 0, 100px);
      background-color: pink;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#funcdef-translate3d">CSS Transforms Level 2<br />
<span class="small">The definition of 'translate3d()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`translate3d()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate3d()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate3d()</a>

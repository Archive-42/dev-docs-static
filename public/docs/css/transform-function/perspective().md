# perspective()

The `perspective()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that sets the distance between the user and the z=0 plane, the perspective from which the viewer would be if the 2-dimensional interface were 3-dimensional. Its result is a [`<transform-function>`](../transform-function) data type.

The `perspective()` transform function is part of the [`transform`](../transform) value applied on the element being transformed. This differs from the [`perspective`](../perspective) and [`perspective-origin`](../perspective-origin) properties which are attached to the parent of a child transformed in 3-dimensional space.

## Syntax

The perspective distance used by `perspective()` is specified by a [`<length>`](../length) value, which represents the distance between the user and the z=0 plane. The z=0 plane is the plane where everything appears in a 2-dimensional view, or the screen. A positive value makes the element appear closer to the user than the rest of the interface, a negative value farther. The greater the value, the further away the perspective of the user is.

    perspective(d)

### Values

d  
Is a [`<length>`](../length) representing the distance from the user to the z=0 plane. If it is 0 or a negative value, no perspective transform is applied.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

This transformation applies to the 3D space and can't be represented on the plane.

This transformation is not a linear transformation in ℝ<sup>3</sup>, and can't be represented using a Cartesian-coordinate matrix.

$\\begin{pmatrix}
1 & 0 & 0 & 0 \\\\
0 & 1 & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & {- 1/d} & 1 \\\\
\\end{pmatrix}$

## Examples

### HTML

    <p>Without perspective:</p>
    <div class="no-perspective-box">
      <div class="face front">A</div>
      <div class="face top">B</div>
      <div class="face left">C</div>
    </div>

    <p>With perspective (9cm):</p>
    <div class="perspective-box-far">
      <div class="face front">A</div>
      <div class="face top">B</div>
      <div class="face left">C</div>
    </div>

    <p>With perspective (4cm):</p>
    <div class="perspective-box-closer">
      <div class="face front">A</div>
      <div class="face top">B</div>
      <div class="face left">C</div>
    </div>

### CSS

    .face {
      position: absolute;
      width: 100px;
      height: 100px;
      line-height: 100px;
      font-size: 100px;
      text-align: center;
    }

    p + div {
      width: 100px;
      height: 100px;
      transform-style: preserve-3d;
      margin-left: 100px;
    }
    .no-perspective-box {
      transform: rotateX(-15deg) rotateY(30deg);
    }

    .perspective-box-far {
      transform: perspective(9cm) rotateX(-15deg) rotateY(30deg);
    }

    .perspective-box-closer {
      transform: perspective(4cm) rotateX(-15deg) rotateY(30deg);
    }

    .top {
      background-color: skyblue;
      transform: rotateX(90deg) translate3d(0, 0, 50px);
    }

    .left {
      background-color: pink;
      transform: rotateY(-90deg) translate3d(0, 0, 50px);
    }

    .front {
      background-color: limegreen;
      transform: translate3d(0, 0, 50px);
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#funcdef-perspective">CSS Transforms Level 2<br />
<span class="small">The definition of 'perspective()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`perspective()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/perspective()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/perspective()</a>

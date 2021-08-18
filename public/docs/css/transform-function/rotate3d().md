# rotate3d()

The `rotate3d()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that rotates an element around a fixed axis in 3D space, without deforming it. Its result is a [`<transform-function>`](../transform-function) data type.

In 3D space, rotations have three degrees of liberty, which together describe a single axis of rotation. The axis of rotation is defined by an \[x, y, z\] vector and pass by the origin (as defined by the [`transform-origin`](../transform-origin) property). If, as specified, the vector is not _normalized_ (i.e., if the sum of the square of its three coordinates is not 1), the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) will normalize it internally. A non-normalizable vector, such as the null vector, \[0, 0, 0\], will cause the rotation to be ignored, but without invaliding the whole CSS property.

**Note:** Unlike rotations in the 2D plane, the composition of 3D rotations is usually not commutative. In other words, the order in which the rotations are applied impacts the result.

## Syntax

The amount of rotation created by `rotate3d()` is specified by three [`<number>`](../number)s and one [`<angle>`](../angle). The `<number>`s represent the x-, y-, and z-coordinates of the vector denoting the axis of rotation. The `<angle>` represents the angle of rotation; if positive, the movement will be clockwise; if negative, it will be counter-clockwise.

    rotate3d(x, y, z, a)

### Values

`x`  
Is a [`<number>`](../number) describing the x-coordinate of the vector denoting the axis of rotation which could between 0 and 1.

`y`  
Is a [`<number>`](../number) describing the y-coordinate of the vector denoting the axis of rotation which could between 0 and 1.

`z`  
Is a [`<number>`](../number) describing the z-coordinate of the vector denoting the axis of rotation which could between 0 and 1.

`a`  
Is an [`<angle>`](../angle) representing the angle of the rotation. A positive angle denotes a clockwise rotation, a negative angle a counter-clockwise one.

Cartesian coordinates on ℝ<sup>2</sup>

This transformation applies to the 3D space and can't be represented on the plane.

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

[<img src="data:image/png;base64,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" width="1021" height="94" />](<rotate3d()/transform-functions-rotate3d_cart.png>)$\\begin{pmatrix}
{1 + \\left( 1 - \\cos\\left( a \\right) \\right)\\left( x^{2} - 1 \\right)} & {z \\cdot \\sin\\left( a \\right) + xy\\left( 1 - \\cos\\left( a \\right) \\right)} & {- y \\cdot \\sin\\left( a \\right) + xz \\cdot \\left( 1 - \\cos\\left( a \\right) \\right)} & \\\\
{- z \\cdot \\sin\\left( a \\right) + xy \\cdot \\left( 1 - \\cos\\left( a \\right) \\right)} & {1 + \\left( 1 - \\cos\\left( a \\right) \\right)\\left( {y2} - 1 \\right)} & {x \\cdot \\sin\\left( a \\right) + yz \\cdot \\left( 1 - \\cos\\left( a \\right) \\right)} & \\\\
{y\\sin\\left( a \\right) + {xz}\\left( 1 - \\cos\\left( a \\right) \\right)} & {- x\\sin\\left( a \\right) + {yz}\\left( 1 - \\cos\\left( a \\right) \\right)} & {1 + \\left( 1 - \\cos\\left( a \\right) \\right)\\left( {z2} - 1 \\right)} & t \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

Homogeneous coordinates on ℝℙ<sup>3</sup>

[<img src="data:image/png;base64,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" width="1054" height="123" />](<rotate3d()/transform-functions-rotate3d_hom4.png>)

## Examples

### Rotating on the y-axis

#### HTML

    <div>Normal</div>
    <div class="rotated">Rotated</div>

#### CSS

    body {
      perspective: 800px;
    }

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .rotated {
      transform: rotate3d(0, 1, 0, 60deg);
      background-color: pink;
    }

#### Result

### Rotating on a custom axis

#### HTML

    <div>Normal</div>
    <div class="rotated">Rotated</div>

#### CSS

    body {
      perspective: 800px;
    }

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .rotated {
      transform: rotate3d(1, 2, -1, 192deg);
      background-color: pink;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#funcdef-rotate3d">CSS Transforms Level 2<br />
<span class="small">The definition of 'rotate3d()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`rotate3d()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate3d()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate3d()</a>

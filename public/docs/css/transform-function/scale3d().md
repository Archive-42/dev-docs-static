# scale3d()

The `scale3d()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that resizes an element in 3D space. Because the amount of scaling is defined by a vector, it can resize different dimensions at different scales. Its result is a [`<transform-function>`](../transform-function) data type.

This scaling transformation is characterized by a three-dimensional vector. Its coordinates define how much scaling is done in each direction. If all three coordinates are equal, the scaling is uniform (_isotropic_) and the aspect ratio of the element is preserved (this is a [homothetic transformation](https://en.wikipedia.org/wiki/Homothetic_transformation)).

When a coordinate value is outside the \[-1, 1\] range, the element grows along that dimension; when inside, it shrinks. If it is negative, the result a [point reflection](https://en.wikipedia.org/wiki/Point_reflection) in that dimension. A value of 1 has no effect.

## Syntax

The `scale3d()` function is specified with three values, which represent the amount of scaling to be applied in each direction.

    scale3d(sx, sy, sz)

### Values

`sx`  
Is a [`<number>`](../number) representing the abscissa of the scaling vector.

`sy`  
Is a [`<number>`](../number) representing the ordinate of the scaling vector.

`sz`  
Is a [`<number>`](../number) representing the z-component of the scaling vector.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

This transformation applies to the 3D space and can't be represented on the plane.

$\\begin{pmatrix}
{sx} & 0 & 0 \\\\
0 & {sy} & 0 \\\\
0 & 0 & {sz} \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
{sx} & 0 & 0 & 0 \\\\
0 & {sy} & 0 & 0 \\\\
0 & 0 & {sz} & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

## Examples

### Without changing the origin

#### HTML

    <div>Normal</div>
    <div class="scaled">Scaled</div>

#### CSS

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .scaled {
      transform: perspective(500px) scale3d(2, 0.7, 0.2) translateZ(100px);
      background-color: pink;
    }

#### Result

### Translating the origin of the transformation

#### HTML

    <div>Normal</div>
    <div class="scaled">Scaled</div>

#### CSS

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .scaled {
      transform: perspective(500px) scale3d(2, 0.7, 0.2) translateZ(100px);
      transform-origin: left;
      background-color: pink;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#funcdef-scale3d">CSS Transforms Level 2<br />
<span class="small">The definition of 'scale3d()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scale3d()`

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
- `scaleZ()`
- `translate3d()`
- `rotate3d()`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale3d()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale3d()</a>

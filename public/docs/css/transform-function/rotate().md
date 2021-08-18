# rotate()

The `rotate()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that rotates an element around a fixed point on the 2D plane, without deforming it. Its result is a [`<transform-function>`](../transform-function) data type.

The fixed point that the element rotates around — mentioned above — is also known as the **transform origin**. This defaults to the center of the element, but you can set your own custom transform origin using the [`transform-origin`](../transform-origin) property.

## Syntax

The amount of rotation created by `rotate()` is specified by an [`<angle>`](../angle). If positive, the movement will be clockwise; if negative, it will be counter-clockwise. A rotation by 180° is called _point reflection_.

    rotate(a)

### Values

a  
Is an [`<angle>`](../angle) representing the angle of the rotation. A positive angle denotes a clockwise rotation, a negative angle a counter-clockwise one.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

$\\begin{pmatrix}
{\\cos\\left( a \\right)} & {- \\sin\\left( a \\right)} \\\\
{\\sin\\left( a \\right)} & {\\cos\\left( a \\right)} \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
{\\cos\\left( a \\right)} & {- \\sin\\left( a \\right)} & 0 \\\\
{\\sin\\left( a \\right)} & {\\cos\\left( a \\right)} & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
{\\cos\\left( a \\right)} & {- \\sin\\left( a \\right)} & 0 \\\\
{\\sin\\left( a \\right)} & {\\cos\\left( a \\right)} & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
{\\cos\\left( a \\right)} & {- \\sin\\left( a \\right)} & 0 & 0 \\\\
{\\sin\\left( a \\right)} & {\\cos\\left( a \\right)} & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[cos(a) sin(a) -sin(a) cos(a) 0 0]`

## Examples

### Basic example

#### HTML

    <div>Normal</div>
    <div class="rotated">Rotated</div>

#### CSS

    div {
      width: 80px;
      height: 80px;
      background-color: skyblue;
    }

    .rotated {
      transform: rotate(45deg); /* Equal to rotateZ(45deg) */
      background-color: pink;
    }

#### Result

### Combining rotation with another transformation

If you want apply multiple transformations to an element, be careful about the order in which you specify your transformations. For example, if you rotate before translating, the translation will be along the new axis of rotation!

#### HTML

    <div>Normal</div>
    <div class="rotate">Rotated</div>
    <div class="rotate-translate">Rotated + Translated</div>
    <div class="translate-rotate">Translated + Rotated</div>

#### CSS

    div {
      position: absolute;
      left: 40px;
      top: 40px;
      width: 100px;
      height: 100px;
      background-color: lightgray;
    }

    .rotate {
      background-color: transparent;
      outline: 2px dashed;
      transform: rotate(45deg);
    }

    .rotate-translate {
      background-color: pink;
      transform: rotate(45deg) translateX(180px);
    }

    .translate-rotate {
      background-color: gold;
      transform: translateX(180px) rotate(45deg);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-rotate">CSS Transforms Level 1<br />
<span class="small">The definition of 'rotate()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`rotate()`

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
- `rotate3d()`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate()</a>

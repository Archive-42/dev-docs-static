# &lt;transform-function&gt;

The `<transform-function>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a transformation that affects an element's appearance. Transformation [functions](css_functions) can rotate, resize, distort, or move an element in 2D or 3D space. It is used in the [`transform`](transform) property.

## Syntax

The `<transform-function>` data type is specified using one of the transformation functions listed below. Each function applies a geometric operation in either 2D or 3D.

### Matrix transformation

`matrix()`  
Describes a homogeneous 2D transformation matrix.

`matrix3d()`  
Describes a 3D transformation as a 4×4 homogeneous matrix.

### Perspective

`perspective()`  
Sets the distance between the user and the z=0 plane.

### Rotation

`rotate()`  
Rotates an element around a fixed point on the 2D plane.

`rotate3d()`  
Rotates an element around a fixed axis in 3D space.

`rotateX()`  
Rotates an element around the horizontal axis.

`rotateY()`  
Rotates an element around the vertical axis.

`rotateZ()`  
Rotates an element around the z-axis.

### Scaling (resizing)

`scale()`  
Scales an element up or down on the 2D plane.

`scale3d()`  
Scales an element up or down in 3D space.

`scaleX()`  
Scales an element up or down horizontally.

`scaleY()`  
Scales an element up or down vertically.

`scaleZ()`  
Scales an element up or down along the z-axis.

### Skewing (distortion)

`skew()`  
Skews an element on the 2D plane.

`skewX()`  
Skews an element in the horizontal direction.

`skewY()`  
Skews an element in the vertical direction.

### Translation (moving)

`translate()`  
Translates an element on the 2D plane.

`translate3d()`  
Translates an element in 3D space.

`translateX()`  
Translates an element horizontally.

`translateY()`  
Translates an element vertically.

`translateZ()`  
Translates an element along the z-axis.

## Description

Various coordinate models can be used to describe an HTML element's size and shape, as well as any transformations applied to it. The most common is the [Cartesian coordinate system](https://en.wikipedia.org/wiki/Cartesian_coordinate_system), although [homogeneous coordinates](https://en.wikipedia.org/wiki/Homogeneous_coordinates) are also sometimes used.

### Cartesian coordinates

[<img src="data:image/png;base64,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" width="228" height="244" />](transform-function/coord_in_r2.png)

In the Cartesian coordinate system, a two-dimensional point is described using two values: an x coordinate (abscissa) and a y coordinate (ordinate). This is represented by the vector notation `(x, y)`.

In CSS (and most computer graphics), the origin `(0, 0)` represents the _top-left_ corner of any element. Positive coordinates are down and to the right of the origin, while negative ones are up and to the left. Thus, a point that's 2 units to the right and 5 units down would be `(2, 5)`, while a point 3 units to the left and 12 units up would be `(-3, -12)`.

### Transformation functions

Transformation functions alter the appearance of an element by manipulating the values of its coordinates. A linear transformation function is described using a 2×2 matrix, like this:

$\\begin{pmatrix}
a & c \\\\
b & d \\\\
\\end{pmatrix}$

The function is applied to an element by using matrix multiplication. Thus, each coordinate changes based on the values in the matrix:

$\\begin{pmatrix}
a & c \\\\
b & d \\\\
\\end{pmatrix}\\begin{pmatrix}
x \\\\
y \\\\
\\end{pmatrix} = \\begin{pmatrix}
{ax + cy} \\\\
{bx + dy} \\\\
\\end{pmatrix}$

It is even possible to apply several transformations in a row:

$\\begin{pmatrix}
a\_{1} & c\_{1} \\\\
b\_{1} & d\_{1} \\\\
\\end{pmatrix}\\begin{pmatrix}
a\_{2} & c\_{2} \\\\
b\_{2} & d\_{2} \\\\
\\end{pmatrix} = \\begin{pmatrix}
{a\_{1}a\_{2} + c\_{1}b\_{2}} & {a\_{1}c\_{2} + c\_{1}d\_{2}} \\\\
{b\_{1}a\_{2} + d\_{1}b\_{2}} & {b\_{1}c\_{2} + d\_{1}d\_{2}} \\\\
\\end{pmatrix}$

With this notation, it is possible to describe, and therefore compose, most common transformations: rotations, scaling, or skewing. (In fact, all transformations that are linear functions can be described.) Composite transformations are effectively applied in order from right to left.

However, one major transformation is not linear, and therefore must be special-cased when using this notation: translation. The translation vector `(tx, ty)` must be expressed separately, as two additional parameters.

**Note:** Though trickier than Cartesian coordinates, [homogeneous coordinates](https://en.wikipedia.org/wiki/Homogeneous_coordinates) in [projective geometry](https://en.wikipedia.org/wiki/Projective_geometry) lead to 3×3 transformation matrices, and can express translations as linear functions.

## Examples

### Transform function comparison

The following example provides a 3D cube created from DOM elements and transforms, and a select menu allowing you to choose different transform functions to transform the cube with, so you can compare the effects of the different types.

Choose one, and the transform is applied to the cube; after 2 seconds, the cube reverts back to its starting state. The cube's starting state is slightly rotated using `transform3d()`, to allow you to see the effect of all the transforms.

#### HTML

    <main>
      <section id="example-element">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
      </section>

      <div class="select-form">
        <label>Select a transform function</label>
        <select>
          <option selected>Choose a function</option>
          <option>rotate(360deg)</option>
          <option>rotateX(360deg)</option>
          <option>rotateY(360deg)</option>
          <option>rotateZ(360deg)</option>
          <option>rotate3d(1, 1, 1, 90deg)</option>
          <option>scale(1.5)</option>
          <option>scaleX(1.5)</option>
          <option>scaleY(1.5)</option>
          <option>scaleZ(1.5)</option>
          <option>scale3d(1, 1.5, 1.5)</option>
          <option>skew(17deg, 13deg)</option>
          <option>skewX(17deg)</option>
          <option>skewY(17deg)</option>
          <option>translate(100px, 100px)</option>
          <option>translateX(100px)</option>
          <option>translateY(100px)</option>
          <option>translateZ(100px)</option>
          <option>translate3d(50px, 50px, 50px)</option>
          <option>perspective(200px)</option>
          <option>matrix(1, 2, -1, 1, 80, 80)</option>
          <option>matrix3d(1,0,0,0,0,1,3,0,0,0,1,0,50,100,0,1.1)</option>
        </select>
      </div>
    </main>

#### CSS

    main {
      width: 400px;
      height: 200px;
      padding: 50px;
      background-image: linear-gradient(135deg, white, cyan, white);
    }

    #example-element {
      width: 100px;
      height: 100px;
      transform-style: preserve-3d;
      transition: transform 1.5s;
      transform: rotate3d(1, 1, 1, 30deg);
    }

    .face {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 100%;
      position: absolute;
      backface-visibility: inherit;
      font-size: 60px;
      color: #fff;
    }

    .front {
        background: rgba(90,90,90,.7);
        transform: translateZ(50px);
    }

    .back {
        background: rgba(0,210,0,.7);
        transform: rotateY(180deg) translateZ(50px);
    }

    .right {
      background: rgba(210,0,0,.7);
      transform: rotateY(90deg) translateZ(50px);
    }

    .left {
      background: rgba(0,0,210,.7);
      transform: rotateY(-90deg) translateZ(50px);
    }

    .top {
      background: rgba(210,210,0,.7);
      transform: rotateX(90deg) translateZ(50px);
    }

    .bottom {
      background: rgba(210,0,210,.7);
      transform: rotateX(-90deg) translateZ(50px);
    }

    .select-form {
      margin-top: 50px;
    }

#### JavaScript

    const selectElem = document.querySelector('select');
    const example = document.querySelector('#example-element');

    selectElem.addEventListener('change', () => {
      if(selectElem.value === 'Choose a function') {
        return;
      } else {
        example.style.transform = `rotate3d(1, 1, 1, 30deg) ${selectElem.value}`;
        setTimeout(function() {
          example.style.transform = 'rotate3d(1, 1, 1, 30deg)';
        }, 2000)
      }
    })

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#transform-functions">CSS Transforms Level 2<br />
<span class="small">The definition of '&lt;transform-function&gt;' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Added 3D transform functions.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-transforms/#transform-functions">CSS Transforms Level 1<br />
<span class="small">The definition of '&lt;transform-function&gt;' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`transform-function`

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

- CSS [`transform`](transform) property

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function</a>

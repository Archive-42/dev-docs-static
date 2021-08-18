# matrix3d()

The `matrix3d()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a 3D transformation as a 4x4 homogeneous matrix. Its result is a [`<transform-function>`](../transform-function) data type.

## Syntax

The `matrix3d()` function is specified with 16 values. They are described in the column-major order.

    matrix3d(a1, b1, c1, d1, a2, b2, c2, d2, a3, b3, c3, d3, a4, b4, c4, d4)

### Values

a1 b1 c1 d1 a2 b2 c2 d2 a3 b3 c3 d3  
Are [`<number>`](../number)s describing the linear transformation.

a4 b4 c4 d4  
Are [`<number>`](../number)s describing the translation to apply.

**Note:** Until Firefox 16, Gecko accepted a [`<length>`](../length) value for a4, b4 and c4.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

This transformation applies to the 3D space and can't be represented on the plane.

A generic 3D [affine transformation](https://en.wikipedia.org/wiki/Affine_transformation) can't be represented using a Cartesian-coordinate matrix, as translations are not linear transformations.

$\\begin{pmatrix}
{a1} & {a2} & {a3} & {a4} \\\\
{b1} & {b2} & {b3} & {b4} \\\\
{c1} & {c2} & {c3} & {c4} \\\\
{d1} & {d2} & {d3} & {d4} \\\\
\\end{pmatrix}$

## Examples

### Cube squashing example

The following example shows a 3D cube created from DOM elements and transforms, which can be hovered/focused to apply a `matrix3d()` transform to it.

#### HTML

    <section id="example-element" tabindex="0">
      <div class="face front">1</div>
      <div class="face back">2</div>
      <div class="face right">3</div>
      <div class="face left">4</div>
      <div class="face top">5</div>
      <div class="face bottom">6</div>
    </section>

#### CSS

    #example-element {
      width: 100px;
      height: 100px;
      transform-style: preserve-3d;
      transition: transform 1.5s;
      transform: rotate3d(1, 1, 1, 30deg);
      margin: 50px auto;
    }

    #example-element:hover, #example-element:focus {
      transform: rotate3d(1, 1, 1, 30deg) matrix3d(1,0,0,0,0,1,6,0,0,0,1,0,50,100,0,1.1);
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

#### Result

### Matrix translation and scale example

Another `transform3d()` example, which implements an animated combined translate and scale.

#### HTML

    <div class="foo">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
    Quos quaerat sit soluta, quisquam exercitationem delectus qui unde in facere
    necessitatibus aut quia porro dolorem nesciunt enim, at consequuntur aliquam esse?
    </div>

#### CSS

    html {
      width: 100%;
    }
    body {
      height: 100vh;
      /* Centering content */
      display: flex;
      flex-flow: row wrap;
      justify-content: center;
      align-content: center;

    }
    .foo {
      width: 50%;
      padding: 1em;
      color: white;
      background: #ff8c66;
      border: 2px dashed black;
      text-align: center;
      font-family: system-ui, sans-serif;
      font-size: 14px;
       /* Setting up animation for better demonstration */
      animation: MotionScale 2s alternate linear infinite;
    }

    @keyframes MotionScale {
      from {
        /*
          Identity matrix is used as basis here.
          The matrix below describes the
          following transformations:
            Translates every X point by -50px
            Translates every Y point by -100px
            Translates every Z point by 0
            Scales down by 10%
        */
        transform: matrix3d(
          1,0,0,0,
          0,1,0,0,
          0,0,1,0,
          -50,-100,0,1.1
        );

      }
      50% {
        transform: matrix3d(
          1,0,0,0,
          0,1,0,0,
          0,0,1,0,
          0,0,0,0.9
        );
      }
      to {
         transform: matrix3d(
          1,0,0,0,
          0,1,0,0,
          0,0,1,0,
          50,100,0,1.1
        )
      }
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#funcdef-matrix3d">CSS Transforms Level 2<br />
<span class="small">The definition of 'matrix3d()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`matrix3d()`

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
- [Understanding the CSS Transforms Matrix](https://dev.opera.com/articles/understanding-the-css-transforms-matrix/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/matrix3d()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/matrix3d()</a>

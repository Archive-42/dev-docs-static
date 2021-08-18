# scale()

The `scale()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) defines a transformation that resizes an element on the 2D plane. Because the amount of scaling is defined by a vector, it can resize the horizontal and vertical dimensions at different scales. Its result is a [`<transform-function>`](../transform-function) data type.

<img src="data:image/png;base64,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" width="392" height="325" />

This scaling transformation is characterized by a two-dimensional vector. Its coordinates define how much scaling is done in each direction. If both coordinates are equal, the scaling is uniform (_isotropic_) and the aspect ratio of the element is preserved (this is a [homothetic transformation](https://en.wikipedia.org/wiki/Homothetic_transformation)).

When a coordinate value is outside the \[-1, 1\] range, the element grows along that dimension; when inside, it shrinks. If it is negative, the result a [point reflection](https://en.wikipedia.org/wiki/Point_reflection) in that dimension. A value of 1 has no effect.

**Note:** The `scale()` function only scales in 2D. To scale in 3D, use `scale3d()` instead.

## Syntax

The `scale()` function is specified with either one or two values, which represent the amount of scaling to be applied in each direction.

    scale(sx)

    scale(sx, sy)

### Values

`sx`  
A [`<number>`](../number) representing the abscissa of the scaling vector.

`sy`  
A [`<number>`](../number) representing the ordinate of the scaling vector. If not defined, its default value is `sx`, resulting in a uniform scaling that preserves the element's aspect ratio.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

$\\begin{pmatrix}
{sx} & 0 \\\\
0 & {sy} \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
{sx} & 0 & 0 \\\\
0 & {sy} & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
{sx} & 0 & 0 \\\\
0 & {sy} & 0 \\\\
0 & 0 & 1 \\\\
\\end{pmatrix}$

$\\begin{pmatrix}
{sx} & 0 & 0 & 0 \\\\
0 & {sy} & 0 & 0 \\\\
0 & 0 & 1 & 0 \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

`[sx 0 0 sy 0 0]`

## Accessibility concerns

Scaling/zooming animations are problematic for accessibility, as they are a common trigger for certain types of migraine. If you need to include such animations on your website, you should provide a control to allow users to turn off animations, preferably site-wide.

Also, consider making use of the [`prefers-reduced-motion`](../@media/prefers-reduced-motion) media feature — use it to write a [media query](../media_queries) that will turn off animations if the user has reduced animation specified in their system preferences.

Find out more:

- [MDN Understanding WCAG, Guideline 2.3 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.3_%e2%80%94_seizures_and_physical_reactions_do_not_design_content_in_a_way_that_is_known_to_cause_seizures_or_physical_reactions)
- [Understanding Success Criterion 2.3.3 | W3C Understanding WCAG 2.1](https://www.w3.org/WAI/WCAG21/Understanding/animation-from-interactions)

## Examples

### Scaling the X and Y dimensions together

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
      transform: scale(0.7); /* Equal to scaleX(0.7) scaleY(0.7) */
      background-color: pink;
    }

#### Result

### Scaling X and Y dimensions separately, and translating the origin

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
      transform: scale(2, 0.5); /* Equal to scaleX(2) scaleY(0.5) */
      transform-origin: left;
      background-color: pink;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms/#funcdef-transform-scale">CSS Transforms Level 1<br />
<span class="small">The definition of 'scale()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scale()`

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
- [`scale3d()`](<scale3d()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale()</a>

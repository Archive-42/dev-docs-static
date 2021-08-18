# linear-gradient()

The `linear-gradient()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) creates an image consisting of a progressive transition between two or more colors along a straight line. Its result is an object of the [`<gradient>`](gradient) data type, which is a special kind of [`<image>`](image).

## Syntax

    /* A gradient tilted 45 degrees,
       starting blue and finishing red */
    linear-gradient(45deg, blue, red);

    /* A gradient going from the bottom right to the top left corner,
       starting blue and finishing red */
    linear-gradient(to left top, blue, red);

    /* Color stop: A gradient going from the bottom to top,
       starting blue, turning green at 40% of its length,
       and finishing red */
    linear-gradient(0deg, blue, green 40%, red);

    /* Color hint: A gradient going from the left to right,
       starting red, getting to the midpoint color
       10% of the way across the length of the gradient,
       taking the rest of the 90% of the length to change to blue */
    linear-gradient(.25turn, red, 10%, blue);

    /* Multi-position color stop: A gradient tilted 45 degrees,
       with a red bottom-left half and a blue top-right half,
       with a hard line where the gradient changes from red to blue */
    linear-gradient(45deg, red 0 50%, blue 50% 100%);

### Values

`<side-or-corner>`  
The position of the gradient line's starting point. If specified, it consists of the word `to` and up to two keywords: one indicates the horizontal side (`left` or `right`), and the other the vertical side (`top` or `bottom`). The order of the side keywords does not matter. If unspecified, it defaults to `to bottom`.

The values `to top`, `to bottom`, `to left`, and `to right` are equivalent to the angles `0deg`, `180deg`, `270deg`, and `90deg`, respectively. The other values are translated into an angle.

[`<angle>`](angle)  
The gradient line's angle of direction. A value of `0deg` is equivalent to `to top`; increasing values rotate clockwise from there.

`<linear-color-stop>`  
A color-stop's [`<color>`](color_value) value, followed by one or two optional stop positions, (each being either a [`<percentage>`](percentage) or a [`<length>`](length) along the gradient's axis).

`<color-hint>`  
The color-hint is an interpolation hint defining how the gradient progresses between adjacent color stops. The length defines at which point between two color stops the gradient color should reach the midpoint of the color transition. If omitted, the midpoint of the color transition is the midpoint between two color stops.

**Note:** Rendering of [color stops in CSS gradients](#gradient_with_multiple_color_stops) follows the same rules as color stops in [SVG gradients](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Gradients).

Note also that the first example above does not exactly render as depicted in Mozilla Firefox (particularly version 80.0b3). You'll have to set the html height property to 100% or 100vh to render as depicted.

## Description

As with any gradient, a linear gradient has [no intrinsic dimensions](image#no_intrinsic); i.e., it has no natural or preferred size, nor a preferred ratio. Its concrete size will match the size of the element it applies to.

To create a linear gradient that repeats so as to fill its container, use the [`repeating-linear-gradient()`](<repeating-linear-gradient()>) function instead.

Because `<gradient>`s belong to the `<image>` data type, they can only be used where `<image>`s can be used. For this reason, `linear-gradient()` won't work on [`background-color`](background-color) and other properties that use the [`<color>`](color_value) data type.

### Composition of a linear gradient

A linear gradient is defined by an axis—the _gradient line_—and two or more _color-stop points_. Each point on the axis is a distinct color; to create a smooth gradient, the `linear-gradient()` function draws a series of colored lines perpendicular to the gradient line, each one matching the color of the point where it intersects the gradient line.

<img src="data:image/png;base64,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" alt="linear-gradient.png" width="309" height="383" />

The gradient line is defined by the center of the box containing the gradient image and by an angle. The colors of the gradient are determined by two or more points: the starting point, the ending point, and, in between, optional color-stop points.

The _starting point_ is the location on the gradient line where the first color begins. The _ending point_ is the point where the last color ends. Each of these two points is defined by the intersection of the gradient line with a perpendicular line passing from the box corner which is in the same quadrant. The ending point can be understood as the symmetrical point of the starting point. These somewhat complex definitions lead to an interesting effect sometimes called _magic corners_: the corners nearest to the starting and ending points have the same color as their respective starting or ending points.

#### Customizing Gradients

By adding more color-stop points on the gradient line, you can create a highly customized transition between multiple colors. A color-stop's position can be explicitly defined by using a [`<length>`](length) or a [`<percentage>`](percentage). If you don't specify the location of a color, it is placed halfway between the one that precedes it and the one that follows it. The following two gradients are equivalent.

    linear-gradient(red, orange, yellow, green, blue);
    linear-gradient(red 0%, orange 25%, yellow 50%, green 75%, blue 100%);

By default, colors transition smoothly from the color at one color stop to the color at the subsequent color stop, with the midpoint between the colors being the half way point between the color transition. You can move this midpoint to any position between two color stops by adding an unlabelled % color hint between the two colors to indicate where the middle of the color transition should be. The following example is solid red from the start to the 10% mark and solid blue from 90% to the end. Between 10% and 90% the color transitions from red to blue, however the midpoint of the transition is at the 30% mark rather than 50% as would have happened without the 30% color hint.

    linear-gradient(red 10%, 30%, blue 90%);

If two or more color stops are at the same location, the transition will be a hard line between the first and last colors declared at that location.

Color stops should be listed in ascending order. Subsequent color stops of lower value will override the value of the previous color stop creating a hard transition. The following changes from red to yellow at the 30% mark, and then transitions from yellow to blue over 35% of the gradient

    linear-gradient(red 40%, yellow 30%, blue 65%);

Multi-position color stop are allowed. A color can be declared as two adjacent color stops by including both positions in the CSS declaration. The following three gradients are equivalent:

    linear-gradient(red 0%, orange 10%, orange 30%, yellow 50%, yellow 70%, green 90%, green 100%);
    linear-gradient(red, orange 10% 30%, yellow 50% 70%, green 90%);
    linear-gradient(red 0%, orange 10% 30%, yellow 50% 70%, green 90% 100%);

By default, if there is no color with a 0% stop, the first color declared will be at that point. Similarly, the last color will continue to the 100% mark, or be at the 100% mark if no length has been declared on that last stop.

## Examples

### Gradient at a 45-degree angle

    body {
      background: linear-gradient(45deg, red, blue);
    }

### Gradient that starts at 60% of the gradient line

    body {
      background: linear-gradient(135deg, orange 60%, cyan);
    }

### Gradient with multi-position color stops

This example uses multi-position color stops, with adjacent colors having the same color stop value, creating a striped effect.

    body {
      background: linear-gradient(to right,
         red 20%, orange 20% 40%, yellow 40% 60%, green 60% 80%, blue 80%);
    }

### More linear-gradient examples

Please see [Using CSS gradients](css_images/using_css_gradients) for more examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#color-stop-syntax">CSS Images Module Level 4<br />
<span class="small">The definition of 'Gradient Color-Stops' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds interpolation hints.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-images-3/#linear-gradients">CSS Images Module Level 3<br />
<span class="small">The definition of 'linear-gradient()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`linear-gradient()`

26

10

12

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

3.6

\["Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

49

44

10

Internet Explorer 5.5 through 9.0 supported gradients via a proprietary filter: `-ms-filter: progid:DXImageTransform.Microsoft.Gradient()`.

12.1

11-15

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

15

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

6.1

5.1

\["Safari 4 was supporting an experimental `-webkit-gradient(linear,…)` function. It is more limited than the later standard version: you cannot specify both a position and an angle like in `linear-gradient()`. This old outdated syntax is still supported for compatibility purposes.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

≤37

≤37

26

18

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

4

\["Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

49

44

12.1

11-14

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

14

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

6.1

6

\["Safari 4 was supporting an experimental `-webkit-gradient(linear,…)` function. It is more limited than the later standard version: you cannot specify both a position and an angle like in `linear-gradient()`. This old outdated syntax is still supported for compatibility purposes.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

1.5

1.0

`doubleposition`

71

79

64

No

58

12.1

71

71

64

50

12.2

10.0

`interpolation_hints`

40

79

36

No

27

6.1

40

40

36

27

6.1

4.0

`to`

26

12

10

10

12.1

6.1

≤37

26

10

14

6.1

1.5

`unitless_0_angle`

26

12

55

46

Accepted only in `-webkit-linear-gradient()` and `-moz-linear-gradient()`, not `linear-gradient()`.

No

16

6.1

≤37

26

55

46

Accepted only in `-webkit-linear-gradient()` and `-moz-linear-gradient()`, not `linear-gradient()`.

14

6.1

1.5

## See also

- [Using CSS gradients](css_images/using_css_gradients)
- Other gradient functions: [`repeating-linear-gradient()`](<repeating-linear-gradient()>), [`radial-gradient()`](<radial-gradient()>), [`repeating-radial-gradient()`](<repeating-radial-gradient()>), [`conic-gradient()`](<conic-gradient()>), [`repeating-conic-gradient()`](<repeating-conic-gradient()>)
- [`<image>`](image)
- [`element()`](<element()>)
- [`image()`](<image()>)
- [`image-set()`](<image-set()>)
- [`cross-fade()`](<cross-fade()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient()</a>

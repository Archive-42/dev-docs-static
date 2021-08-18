# repeating-radial-gradient()

The `repeating-radial-gradient()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) creates an image consisting of repeating gradients that radiate from an origin. It is similar to [`radial-gradient()`](<radial-gradient()>) and takes the same arguments, but it repeats the color stops infinitely in all directions so as to cover its entire container, similar to [`repeating-linear-gradient()`](<repeating-linear-gradient()>) . The function's result is an object of the [`<gradient>`](gradient) data type, which is a special kind of [`<image>`](image).

With each repetition, the positions of the color stops are shifted by a multiple of the dimensions of the basic radial gradient (the distance between the last color stop and the first). Thus, the position of each ending color stop coincides with a starting color stop; if the color values are different, this will result in a sharp visual transition, which can be mitigated by repeating the first color as the last color.

As with any gradient, a repeating radial gradient has [no intrinsic dimensions](image#no_intrinsic); i.e., it has no natural or preferred size, nor a preferred ratio. Its concrete size will match the size of the element it applies to.

Because `<gradient>`s belong to the `<image>` data type, they can only be used where `<image>`s can be used. For this reason, `repeating-radial-gradient()` won't work on [`background-color`](background-color) and other properties that use the [`<color>`](color_value) data type.

## Syntax

    /* A gradient at the center of its container,
       starting red, changing to blue, and finishing green,
       with the colors repeating every 30px */
    repeating-radial-gradient(circle at center, red 0, blue, green 30px);

    /* An elliptical gradient near the top left of its container,
       starting red, changing to green and back again,
       repeating five times between the center and the bottom right corner,
       and only once between the center and the top left corner */
    repeating-radial-gradient(farthest-corner at 20% 20%, red 0, green, red 20%);

### Values

[`<position>`](position_value)  
The position of the gradient, interpreted in the same way as [`background-position`](background-position) or [`transform-origin`](transform-origin). If unspecified, it defaults to `center`.

`<shape>`  
The gradient's shape. The value can be `circle` (meaning that the gradient's shape is a circle with constant radius) or `ellipse` (meaning that the shape is an axis-aligned ellipse). If unspecified, it defaults to `ellipse`.

`<extent-keyword>`  
A keyword describing how big the ending shape must be. The possible values are:

<table><thead><tr class="header"><th>Keyword</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>closest-side</code></td><td>The gradient's ending shape meets the side of the box closest to its center (for circles) or meets both the vertical and horizontal sides closest to the center (for ellipses).</td></tr><tr class="even"><td><code>closest-corner</code></td><td>The gradient's ending shape is sized so that it exactly meets the closest corner of the box from its center.</td></tr><tr class="odd"><td><code>farthest-side</code></td><td>Similar to <code>closest-side</code>, except the ending shape is sized to meet the side of the box farthest from its center (or vertical and horizontal sides).</td></tr><tr class="even"><td><code>farthest-corner</code></td><td>The gradient's ending shape is sized so that it exactly meets the farthest corner of the box from its center.</td></tr></tbody></table>

**Note:** Early implementations of this function included other keywords (`cover` and `contain`) as synonyms of the standard `farthest-corner` and `closest-side`, respectively. Use the standard keywords only, as some implementations have already dropped those older variants.

`<color-stop>`  
A color-stop's [`<color>`](color_value) value, followed by an optional stop position (either a [`<percentage>`](percentage) or a [`<length>`](length) along the gradient's axis). A percentage of `0%`, or a length of `0`, represents the center of the gradient; the value `100%` represents the intersection of the ending shape with the virtual gradient ray. Percentage values in between are linearly positioned on the virtual gradient ray.

### Formal syntax

    repeating-radial-gradient(
           [[ circle  || <length> ]                     [at <position>]? , |
            [ ellipse || [<length> | <percentage> ]{2}] [at <position>]? , |
            [[ circle | ellipse ] || <extent-keyword> ] [at <position>]? , |
                                                         at <position>   ,    <color-stop-list> )
            \---------------------------------------------------------------/\-----------------/
                      Contour, size and position of the ending shape          List of color stops

    where <extent-keyword> = closest-corner | closest-side | farthest-corner | farthest-side
       and <color-stop-list> = [ <linear-color-stop> [, <color-hint>? ]? ]#, <linear-color-stop>
       and <linear-color-stop> = <color> [ <color-stop-length> ]?
       and <color-stop-length> = [ <percentage> | <length> ]{1,2}
       and <color-hint> = [ <percentage> | <length> ]

## Examples

### Black and white gradient

    .radial-gradient {
      background: repeating-radial-gradient(black, black 5px, white 5px, white 10px);
    }

### Farthest-corner

    .radial-gradient {
      background: repeating-radial-gradient(ellipse farthest-corner at 20% 20%,
          red, black 5%, blue 5%, green 10%);
      background: repeating-radial-gradient(ellipse farthest-corner at 20% 20%,
          red 0 5%, green 5% 10%);
    }

The elliptical gradient will be centered 20% from the top left, and will repeat 10 times between the center and the farthest corner (the bottom right corner). Browsers supporting multi position color stops will display a red and green striped ellipse. Browsers not supporting the syntax yet will see a gradient that goes from red to black and then from blue to green.

**Note:** Please see [Using CSS gradients](css_images/using_css_gradients) for more examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-3/#repeating-gradients">CSS Images Module Level 3<br />
<span class="small">The definition of 'repeating-radial-gradient()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`repeating-radial-gradient()`

26

10

12

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

3.6

Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.

49

44

10

12.1

15

12-15

6.1

5.1

Safari 4 was supporting an experimental `-webkit-gradient(radial,…)` function. This old outdated syntax is still supported for compatibility purposes.

4.4

≤37

26

18

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

10

Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.

49

44

12.1

14

12-14

7

6

Safari 4 was supporting an experimental `-webkit-gradient(radial,…)` function. This old outdated syntax is still supported for compatibility purposes.

1.5

1.0

`at`

26

12

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

10

Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.

49

44

10

15

12-15

No

≤37

26

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

10

Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.

49

44

14

12-14

No

1.5

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

46

27

7

4.0

## See also

- [Using CSS gradients](css_images/using_css_gradients)
- Other gradient functions: [`radial-gradient()`](<radial-gradient()>), [`linear-gradient()`](<linear-gradient()>), [`repeating-linear-gradient()`](<repeating-linear-gradient()>), [`conic-gradient()`](<conic-gradient()>), [`repeating-conic-gradient()`](<repeating-conic-gradient()>)
- [`<image>`](image)
- [`image()`](<image()>)
- [`element()`](<element()>)
- [`image-set()`](<image-set()>)
- [`cross-fade()`](<cross-fade()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/repeating-radial-gradient()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/repeating-radial-gradient()</a>

# conic-gradient()

The `conic-gradient()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) creates an image consisting of a gradient with color transitions rotated around a center point (rather than radiating from the center). Example conic gradients include pie charts and color wheels. The result of the `conic-gradient()` function is an object of the [`<gradient>`](gradient) data type, which is a special kind of [`<image>`](image).

## Syntax

    /* A conic gradient rotated 45 degrees,
       starting blue and finishing red */
    conic-gradient(from 45deg, blue, red);

    /* A bluish purple box: the gradient goes from blue to red,
       but as only the bottom right quadrant is visible, as the
       center of the conic gradient is in at the top left corner */
    conic-gradient(from 90deg at 0 0, blue, red);

    /* Colorwheel */
    background: conic-gradient(
        hsl(360, 100%, 50%),
        hsl(315, 100%, 50%),
        hsl(270, 100%, 50%),
        hsl(225, 100%, 50%),
        hsl(180, 100%, 50%),
        hsl(135, 100%, 50%),
        hsl(90, 100%, 50%),
        hsl(45, 100%, 50%),
        hsl(0, 100%, 50%)
    );

### Values

[`<angle>`](angle)  
Preceded by the `from` keyterm, and taking an angle as its value, defines the gradient rotation in clockwise direction.

`<position>`  
Using the same length, order and keyterm values as the [background-position](background-position) property, the position defines center of the gradient. If omitted, the default value is `center`, meaning the gradient will be centered, .

`<angular-color-stop>`  
A color-stop's [`<color>`](color_value) value, followed by one or two optional stop positions, (an [`<angle>`](angle) along the gradient's circumference axis).

`<color-hint>`  
Th color-hint is an interpolation hint defining how the gradient progresses between adjacent color stops. The length defines at which point between two color stops the gradient color should reach the midpoint of the color transition. If omitted, the midpoint of the color transition is the midpoint between two color stops.

**Note:** Rendering of [color stops in CSS gradients](#gradient_with_multiple_color_stops) follows the same rules as color stops in [SVG gradients](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Gradients).

## Description

As with any gradient, a conic gradient has [no intrinsic dimensions](image#no_intrinsic); i.e., it has no natural or preferred size, nor a preferred ratio. Its concrete size will match the size of the element it applies to, or size of the `<image>` is set to something other than the element size.

To create a conic gradient that repeats so as to fill a 360 degree rotation, use the [`repeating-conic-gradient()`](<repeating-conic-gradient()>) function instead.

Because `<gradient>`s belong to the `<image>` data type, they can only be used where `<image>`s can be used. For this reason, `conic-gradient()` won't work on [`background-color`](background-color) and other properties that use the [`<color>`](color_value) data type.

Why is it called a "conic" gradient? If the color stops are much lighter on one side than the other, it can look like a cone from above.

### Composition of a conic gradient

The conic-gradient syntax is similar to the radial-gradient syntax, but the color-stops are placed around a gradient arc, the circumference of a circle, rather than on the gradient line emerging from the center of the gradient. With conic gradients, the colors transition as if spun around the center of a circle, starting at the top and going clockwise. In a radial gradient, the colors transition from the center of an ellipse, outward, in all directions.

<img src="data:image/png;base64,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" alt="color stops along the circumference of a conic gradient and the axis of a radial gradient." width="515" height="258" />

A conic gradient is specified by indicating a rotation angle, the center of the gradient, and then specifying a list of color-stops. Unlike linear and radial gradients, whose color-stops are placed by specifying a [length](length), the color-stops of a conic gradient are specified with an [angle](angle). Units include `deg` for degrees, `grad` for gradients, `rad` for radians, and `turn` for turns. There are 360 degrees, 400 gradians, 2π radians, and 1 turn in a circle. Browsers supporting conic gradients also accept percent values, with 100% equaling 360 degrees, but this is not in the specification.

Similar to radial gradients, the conic gradient syntax provides for positioning the center of the gradient anywhere within, or even outside, the image. The values for the position are similar to the syntax for 2-value background-position.

The gradient arc is the circumference of the gradient. The _starting point_ of the gradient or arc is north, or 12:00pm. The gradient is then rotated by the _from_ angle. The colors of the gradient are determined by the angled color stops, their starting points, ending points, and, in between, and optional angled color-stop points. The transitions between colors can be altered with color hints between adjacent colors' color stops.

#### Customizing gradients

By adding more angled color-stop points on the gradient arc, you can create a highly customized transition between multiple colors. A color-stop's position can be explicitly defined by using an [`<angle>`](angle). If you don't specify the location of a color stop, it is placed halfway between the one that precedes it and the one that follows it. If you don't specify an angle for the first or last color stop, their values are 0deg and 360deg respectively. The following two gradients are equivalent

    conic-gradient(red, orange, yellow, green, blue);
    conic-gradient(red 0deg, orange 90deg, yellow 180deg, green 270deg, blue 360deg);

By default, colors transition smoothly from the color at one color stop to the color at the subsequent color stop, with the midpoint between the colors being the half way point between the color transition. You can move this color transition midpoint to any point between two color stops by adding a color hint, indicating where the middle of the color transition should be. The following is solid red from the start to the 10% mark, transitions from red to blue over 80% of the turn, with the final 10% being solid blue. The midpoint of the red to blue gradient change, however, is at the 20% mark rather than the 50% mark as would have happened without the 80grad, or 20%, color hint.

    conic-gradient(red 40grad, 80grad, blue 360grad);

If two or more color stops are at the same location, the transition will be a hard line between the first and last colors declared at that location. To use conic gradients to create pie charts --- which is NOT the correct way to create pie charts as background images are not accessible -- use hard color stops, where the color stop angles for two adjacent color stops are the same. The easiest way to do this is to use multiple position colors stops. The following two declarations are equivalent:

    conic-gradient(#fff 0.09turn, #bbb 0.09turn, #bbb 0.27turn, #666 0.27turn, #666 0.54turn, #000 0.54turn);
    conic-gradient(#fff 0turn 0.09turn, #bbb 0.09turn 0.27turn, #666 0.27turn 0.54turn, #000 0.54turn 1turn);

Color stops should be listed in ascending order. Subsequent color stops of lower value will override the value of the previous color stop creating a hard transition. The following changes from red to yellow at the 30% mark, and then transitions from yellow to blue over 35% of the gradient

    conic-gradient(red .8rad, yellow .6rad, blue 1.3rad);

There are other effects you can create with conic gradients. Oddly, a checkerboard is one of them. By creating quadrants with an upper left and lower right white quadrant and lower left and upper right black quadrants, then repeating the gradient 16 times (four times across and four times down) you can make a checkerboard.

    conic-gradient(#fff 90deg, #000 0.25turn 0.5turn, #fff 1rad 1.5rad, #000 300grad);
    background-size: 25% 25%;

And, yes, you can mix and match different angle units, but don't. The above is hard to read.

## Accessibility concerns

Browsers do not provide any special information on background images to assistive technology. This is important primarily for screen readers, as a screen reader will not announce its presence and therefore convey nothing to its users. While it is possible to create pie charts, checkerboards, and other effects with conic gradients, CSS images provide no native way to assign alternative text, and therefore the image represented by the conic gradient will not be accessible to screen reader users. If the image contains information critical to understanding the page's overall purpose, it is better to describe it semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%e2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

## Examples

### Gradient at 40-degrees

    div {
      background-image:
         conic-gradient(from 40deg, #fff, #000);
    }

### Off-centered gradient

    div {
      background: conic-gradient(from 0deg at 0% 25%, blue, green, yellow 180deg);
    }

### Gradient pie-chart

This example uses multi-position color stops, with adjacent colors having the same color stop value, creating a striped effect.

    div {
      background: conic-gradient(
         red 36deg, orange 36deg 170deg, yellow 170deg);
      border-radius: 50%
    }

### Checkerboard

    div {
      background:
         conic-gradient(#fff 0.25turn, #000 0.25turn 0.5turn, #fff 0.5turn 0.75turn, #000 0.75turn)
         top left / 25% 25% repeat;
      border: 1px solid;
    }

### More conic-gradient examples

Please see [Using CSS gradients](css_images/using_css_gradients) for more examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#conic-gradients">CSS Images Module Level 4<br />
<span class="small">The definition of 'conic-gradient()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`conic-gradient()`

69

79

83

75

No

56

12.1

69

69

83

79

48

12.2

10.0

`doubleposition`

72

79

83

No

60

12.1

72

72

83

51

12.2

11.0

## See also

- [Using CSS gradients](css_images/using_css_gradients)
- Other gradient functions: [`repeating-conic-gradient()`](<repeating-conic-gradient()>), [`linear-gradient()`](<linear-gradient()>), [`repeating-linear-gradient()`](<repeating-linear-gradient()>), [`radial-gradient()`](<radial-gradient()>), [`repeating-radial-gradient()`](<repeating-radial-gradient()>)
- [`<image>`](image)
- [`image()`](<image()>)
- [`element()`](<element()>)
- [`image-set()`](<image-set()>)
- [`cross-fade()`](<cross-fade()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient()</a>

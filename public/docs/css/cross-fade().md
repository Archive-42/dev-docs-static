# cross-fade()

The `cross-fade()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) can be used to blend two or more images at a defined transparency. It can be used for many simple image manipulations, such as tinting an image with a solid color or highlighting a particular area of the page by combining an image with a radial gradient.

## Syntax

**Important**: The specification and current implementations have different syntaxes. The specification syntax is explained first.

### Specification syntax

The `cross-fade()` function takes a list of images with a percentage defining how much of each image is retained in terms of opacity when it is blended with the other images. The percent value must be coded without quotes, must contain the “%” symbol, and its value must be between 0% and 100%.

The function can be used in CSS anywhere an ordinary image reference can be used.

#### Cross-fade percentages

Think of the percentage as an opacity value for each image. This means a value of 0% means the image is fully transparent while a value of 100% makes the image fully opaque.

    cross-fade( url(white.png) 0%, url(black.png) 100%); /* fully black */
    cross-fade( url(white.png) 25%, url(black.png) 75%); /* 25% white, 75% black */
    cross-fade( url(white.png) 50%, url(black.png) 50%); /* 50% white, 50% black */
    cross-fade( url(white.png) 75%, url(black.png) 25%); /* 75% white, 25% black */
    cross-fade( url(white.png) 100%, url(black.png) 0%); /* fully white */
    cross-fade( url(green.png) 75%, url(red.png) 75%); /* both green and red at 75% */

If any percentages are omitted, all the specified percentages are summed together and subtracted from `100%`. If the result is greater than 0%, the result is then divided equally between all images with omitted percentages.

In the simplest case, two images are faded between each other. To do that, only one of the images needs to have a percentage, the other one will be faded accordingly. For example, a value of 0% defined for the first image yields only the second image, while 100% yields only the first. A 25% value renders the first image at 25% and the second at 75%. The 75% value is the inverse, showing the first image at 75% and the second at 25%.

The above could also have been written as:

    cross-fade( url(white.png) 0%,   url(black.png)); /* fully black */
    cross-fade( url(white.png) 25%,  url(black.png)); /* 25% white, 75% black */
    cross-fade( url(white.png),      url(black.png)); /* 50% white, 50% black */
    cross-fade( url(white.png) 75%,  url(black.png)); /* 75% white, 25% black */
    cross-fade( url(white.png) 100%, url(black.png)); /* fully white */
    cross-fade( url(green.png) 75%, url(red.png) 75%); /* both green and red at 75% */

If no percentages are declared, both the images will be 50% opaque, with a cross-fade rendering as an even merge of both images. The 50%/50% example seen above did not need to have the percentages listed, as when a percentage value is omitted, the included percentages are added together and subtracted from 100%. The result, if greater than 0, is then divided equally between all images with omitted percentages.

In the last example, the sum of both percentages is not 100%, and therefore both images include their respective opacities.

If no percentages are declared and three images are included, each image will be 33.33% opaque. The two following are lines (almost) identical:

    cross-fade( url(red.png), url(yellow.png), url(blue.png)); /* all three will be 33.3333% opaque */
    cross-fade( url(red.png) 33.33%, url(yellow.png) 33.33%, url(blue.png) 33.33%);

### Older, implemented syntax

    cross-fade( <image>, <image>, <percentage> )

The specification for the `cross-fade()` function allows for multiple images and for each image to have transparency values independent of the other values. This was not always the case. The [original syntax](https://developer.mozilla.org/en-US/docs/Web), which has been implemented in some browsers, only allowed for two images, with the sum of the transparency of those two images being exactly 100%. The original syntax is supported in Safari and supported with the `-webkit-` prefix in Chrome, Opera, and other blink-based browsers.

    cross-fade(url(white.png), url(black.png), 0%);   /* fully black */
    cross-fade(url(white.png), url(black.png), 25%);  /* 25% white, 75% black */
    cross-fade(url(white.png), url(black.png), 50%);  /* 50% white, 50% black */
    cross-fade(url(white.png), url(black.png), 75%);  /* 75% white, 25% black */
    cross-fade(url(white.png), url(black.png), 100%); /* fully white */

In the implemented syntax, the two comma-separated images are declared first, followed by a comma and required percent value. Omitting the comma or percent invalidates the value. The percent is the opacity of the first declared image. The included percentage is subtracted from <span class="css">100%, with the difference being the opacity of the second image</span>.

The green/red example (with the percentages totalling 150%) and the yellow/red/blue example (with three images) from the specification syntax section, are not possible in this implementation.

## Accessibility concerns

Browsers do not provide any special information on background images to assistive technology. This is important primarily for screen readers, as a screen reader will not announce its presence and therefore convey nothing to its users. If the image contains information critical to understanding the page's overall purpose, it is better to describe it semantically in the document. When using background images, make sure the contrast in color is great enough that any text is legible over the image as well as if the images is missing.

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%e2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

## Formal syntax

    cross-fade( <cf-mixing-image> , <cf-final-image>? )where
    <cf-mixing-image> = <percentage>? && <image>
    <cf-final-image> = <image> | <color>where
    <image> = <url> | <image()> | <image-set()> | <element()> | <paint()> | <cross-fade()> | <gradient>
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <image()> = image( <image-tags>? [ <image-src>? , <color>? ]! )
    <image-set()> = image-set( <image-set-option># )
    <element()> = element( <id-selector> )
    <paint()> = paint( <ident>, <declaration-value>? )
    <cross-fade()> = cross-fade( <cf-mixing-image> , <cf-final-image>? )
    <gradient> = <linear-gradient()> | <repeating-linear-gradient()> | <radial-gradient()> | <repeating-radial-gradient()> | <conic-gradient()>
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <image-tags> = ltr | rtl
    <image-src> = <url> | <string>
    <image-set-option> = [ <image> | <string> ] <resolution>
    <id-selector> = <hash-token>
    <linear-gradient()> = linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
    <repeating-linear-gradient()> = repeating-linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
    <radial-gradient()> = radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
    <repeating-radial-gradient()> = repeating-radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
    <conic-gradient()> = conic-gradient( [ from <angle> ]? [ at <position> ]?, <angular-color-stop-list> )
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>where
    <side-or-corner> = [ left | right ] || [ top | bottom ]
    <color-stop-list> = [ <linear-color-stop> [, <linear-color-hint>]? ]# , <linear-color-stop>
    <ending-shape> = circle | ellipse
    <size> = closest-side | farthest-side | closest-corner | farthest-corner | <length> | <length-percentage>{2}
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]
    <angular-color-stop-list> = [ <angular-color-stop> [, <angular-color-hint>]? ]# , <angular-color-stop>where
    <linear-color-stop> = <color> <color-stop-length>?
    <linear-color-hint> = <length-percentage>
    <length-percentage> = <length> | <percentage>
    <angular-color-stop> = <color> && <color-stop-angle>?
    <angular-color-hint> = <angle-percentage>where
    <color-stop-length> = <length-percentage>{1,2}
    <color-stop-angle> = <angle-percentage>{1,2}
    <angle-percentage> = <angle> | <percentage>

## Examples

### Older syntax for cross-fade

#### HTML

    <div class="crossfade"></div>

#### CSS

    .crossfade {
        width: 300px;
        height: 300px;
        background-image: -webkit-cross-fade(
            url('https://mdn.mozillademos.org/files/8543/br.png'),
            url('https://mdn.mozillademos.org/files/8545/tr.png'),
            75%);
        background-image: cross-fade(
            url('https://mdn.mozillademos.org/files/8543/br.png'),
            url('https://mdn.mozillademos.org/files/8545/tr.png'),
            75%);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#cross-fade-function">CSS Images Module Level 4<br />
<span class="small">The definition of 'cross-fade()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`cross-fade()`

17

Supports the original dual-image with percentage implementation only.

79

Supports the original dual-image with percentage implementation only.

No

No

15

Supports the original dual-image with percentage implementation only.

10

Supports the original dual-image with percentage implementation only.

5.1

Supports the original dual-image with percentage implementation only.

≤37

Supports the original dual-image with percentage implementation only.

18

Supports the original dual-image with percentage implementation only.

No

14

Supports the original dual-image with percentage implementation only.

9.3

Support for the original dual-image with percentage implementation only.

5

Supports the original dual-image with percentage implementation only.

1.0

Support for the original dual-image with percentage implementation only.

## See also

- [`<image>`](image)
- [`url()`](<url()>)
- [`image()`](<image()>)
- [`image-set()`](<image-set()>)
- [`element()`](<element()>)
- [Using CSS gradients](css_images/using_css_gradients)
- Gradient functions: [`linear-gradient()`](<linear-gradient()>), [`radial-gradient()`](<radial-gradient()>), [`repeating-linear-gradient()`](<repeating-linear-gradient()>), [`repeating-radial-gradient()`](<repeating-radial-gradient()>), [`conic-gradient()`](<conic-gradient()>),

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/cross-fade()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/cross-fade()</a>

# mask-image

The `mask-image` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the image that is used as mask layer for an element.

    /* Keyword value */
    mask-image: none;

    /* <mask-source> value */
    mask-image: url(masks.svg#mask1);

    /* <image> values */
    mask-image: linear-gradient(rgba(0, 0, 0, 1.0), transparent);
    mask-image: image(url(mask.png), skyblue);

    /* Multiple values */
    mask-image: image(url(mask.png), skyblue), linear-gradient(rgba(0, 0, 0, 1.0), transparent);

    /* Global values */
    mask-image: inherit;
    mask-image: initial;
    mask-image: unset;

## Syntax

### Values

`none`  
This keyword is interpreted as a transparent black image layer.

`<mask-source>`  
A [`url()`](<url()>) reference to a [`<mask>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/mask) or to a CSS image.

[`<image>`](image)  
An image value used as mask image layer.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, but with <a href="url()"><code>url()</code></a> values made absolute</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <mask-reference>#where
    <mask-reference> = none | <image> | <mask-source>where
    <image> = <url> | <image()> | <image-set()> | <element()> | <paint()> | <cross-fade()> | <gradient>
    <mask-source> = <url>where
    <image()> = image( <image-tags>? [ <image-src>? , <color>? ]! )
    <image-set()> = image-set( <image-set-option># )
    <element()> = element( <id-selector> )
    <paint()> = paint( <ident>, <declaration-value>? )
    <cross-fade()> = cross-fade( <cf-mixing-image> , <cf-final-image>? )
    <gradient> = <linear-gradient()> | <repeating-linear-gradient()> | <radial-gradient()> | <repeating-radial-gradient()> | <conic-gradient()>where
    <image-tags> = ltr | rtl
    <image-src> = <url> | <string>
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>
    <image-set-option> = [ <image> | <string> ] <resolution>
    <id-selector> = <hash-token>
    <cf-mixing-image> = <percentage>? && <image>
    <cf-final-image> = <image> | <color>
    <linear-gradient()> = linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
    <repeating-linear-gradient()> = repeating-linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )
    <radial-gradient()> = radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
    <repeating-radial-gradient()> = repeating-radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )
    <conic-gradient()> = conic-gradient( [ from <angle> ]? [ at <position> ]?, <angular-color-stop-list> )where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <side-or-corner> = [ left | right ] || [ top | bottom ]
    <color-stop-list> = [ <linear-color-stop> [, <linear-color-hint>]? ]# , <linear-color-stop>
    <ending-shape> = circle | ellipse
    <size> = closest-side | farthest-side | closest-corner | farthest-corner | <length> | <length-percentage>{2}
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]
    <angular-color-stop-list> = [ <angular-color-stop> [, <angular-color-hint>]? ]# , <angular-color-stop>where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>
    <linear-color-stop> = <color> <color-stop-length>?
    <linear-color-hint> = <length-percentage>
    <length-percentage> = <length> | <percentage>
    <angular-color-stop> = <color> && <color-stop-angle>?
    <angular-color-hint> = <angle-percentage>where
    <color-stop-length> = <length-percentage>{1,2}
    <color-stop-angle> = <angle-percentage>{1,2}
    <angle-percentage> = <angle> | <percentage>

## Examples

### Setting a mask image with a URL

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-mask-image">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask-image' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mask-image`

1

From version 8, Chrome added support for gradient values. Initially, Chrome supported only `-webkit-` prefixed values for gradients (such as `-webkit-linear-gradient()`). Later, support for unprefixed values was added.

16

53

No

15

4

Initially, Safari supported only `-webkit-` prefixed values for gradients (such as `-webkit-linear-gradient()`). Later, support for unprefixed values was added.

2

Initially, Android supported only `-webkit-` prefixed values for gradients (such as `-webkit-linear-gradient()`). Later, support for unprefixed values was added.

18

From version 8, Chrome added support for gradient values. Initially, Chrome supported only `-webkit-` prefixed values for gradients (such as `-webkit-linear-gradient()`). Later, support for unprefixed values was added.

53

14

3.2

Initially, Safari supported only `-webkit-` prefixed values for gradients (such as `-webkit-linear-gradient()`). Later, support for unprefixed values was added.

1.0

`multiple_mask_images`

1

18

53

No

15

4

≤37

18

53

14

3.2

1.0

`svg_masks`

8

18

53

No

15

4

≤37

18

53

14

3.2

1.0

## See also

- [Clipping and Masking in CSS](https://css-tricks.com/clipping-masking-css/)
- [Apply effects to images with CSS's mask-image property](https://web.dev/css-masking/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image</a>

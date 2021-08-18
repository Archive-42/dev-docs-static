# mask

The `mask` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) hides an element (partially or fully) by masking or clipping the image at specific points.

As well as the properties listed below, the `mask` shorthand also resets [`mask-border`](mask-border) to its initial value. It is therefore recommended to use the `mask` shorthand rather than other shorthands or the individual properties to override any mask settings earlier in the cascade. This will ensure that `mask-border` has also been reset to allow the new styles to take effect.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`mask-clip`](mask-clip)
- [`mask-composite`](mask-composite)
- [`mask-image`](mask-image)
- [`mask-mode`](mask-mode)
- [`mask-origin`](mask-origin)
- [`mask-position`](mask-position)
- [`mask-repeat`](mask-repeat)
- [`mask-size`](mask-size)

## Syntax

    /* Keyword values */
    mask: none;

    /* Image values */
    mask: url(mask.png);                       /* Pixel image used as mask */
    mask: url(masks.svg#star);                 /* Element within SVG graphic used as mask */

    /* Combined values */
    mask: url(masks.svg#star) luminance;       /* Element within SVG graphic used as luminance mask */
    mask: url(masks.svg#star) 40px 20px;       /* Element within SVG graphic used as mask positioned 40px from the top and 20px from the left */
    mask: url(masks.svg#star) 0 0/50px 50px;   /* Element within SVG graphic used as mask with a width and height of 50px */
    mask: url(masks.svg#star) repeat-x;        /* Element within SVG graphic used as horizontally repeated mask */
    mask: url(masks.svg#star) stroke-box;      /* Element within SVG graphic used as mask extending to the box enclosed by the stroke */
    mask: url(masks.svg#star) exclude;         /* Element within SVG graphic used as mask and combined with background using non-overlapping parts */

    /* Global values */
    mask: inherit;
    mask: initial;
    mask: unset;

    /* Multiple masks */
    mask: url(masks.svg#star) left / 16px repeat-y,    /* Element within SVG graphic is used as a mask on the left-hand side with a width of 16px */
          url(masks.svg#circle) right / 16px repeat-y; /* Element within SVG graphic is used as a mask on the right-hand side with a width of 16px */

### Values

`<mask-reference>`  
Sets the mask image source. See [`mask-image`](mask-image).

`<masking-mode>`  
Sets the masking mode of the mask image. See [`mask-mode`](mask-mode).

`<position>`  
Sets the position of the mask image. See [`mask-position`](mask-position).

`<bg-size>`  
Sets the size of the mask image. See [`mask-size`](mask-size).

`<repeat-style>`  
Sets the repetition of the mask image. See [`mask-repeat`](mask-repeat).

`<geometry-box>`  
If only one `<geometry-box>` value is given, it sets both [`mask-origin`](mask-origin) and [`mask-clip`](mask-clip). If two `<geometry-box>` values are present, then the first sets [`mask-origin`](mask-origin) and the second sets [`mask-clip`](mask-clip).

`<geometry-box> | no-clip`  
Sets the area that is affected by the mask image. See [`mask-clip`](mask-clip).

`<compositing-operator>`  
Sets the compositing operation used on the current mask layer. See [`mask-composite`](mask-composite).

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="mask-image"><code>mask-image</code></a>: <code>none</code></li><li><a href="mask-mode"><code>mask-mode</code></a>: <code>match-source</code></li><li><a href="mask-repeat"><code>mask-repeat</code></a>: <code>no-repeat</code></li><li><a href="mask-position"><code>mask-position</code></a>: <code>center</code></li><li><a href="mask-clip"><code>mask-clip</code></a>: <code>border-box</code></li><li><a href="mask-origin"><code>mask-origin</code></a>: <code>border-box</code></li><li><a href="mask-size"><code>mask-size</code></a>: <code>auto</code></li><li><a href="mask-composite"><code>mask-composite</code></a>: <code>add</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="mask-position"><code>mask-position</code></a>: refer to size of mask painting area minus size of mask layer image (see the text for <a href="background-position"><code>background-position</code></a>)</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="mask-image"><code>mask-image</code></a>: as specified, but with <a href="url()"><code>url()</code></a> values made absolute</li><li><a href="mask-mode"><code>mask-mode</code></a>: as specified</li><li><a href="mask-repeat"><code>mask-repeat</code></a>: Consists of two keywords, one per dimension</li><li><a href="mask-position"><code>mask-position</code></a>: Consists of two keywords representing the origin and two offsets from that origin, each given as an absolute length (if given a &lt;length&gt;), otherwise as a percentage.</li><li><a href="mask-clip"><code>mask-clip</code></a>: as specified</li><li><a href="mask-origin"><code>mask-origin</code></a>: as specified</li><li><a href="mask-size"><code>mask-size</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="mask-composite"><code>mask-composite</code></a>: as specified</li></ul></td></tr><tr class="even"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="mask-image"><code>mask-image</code></a>: discrete</li><li><a href="mask-mode"><code>mask-mode</code></a>: discrete</li><li><a href="mask-repeat"><code>mask-repeat</code></a>: discrete</li><li><a href="mask-position"><code>mask-position</code></a>: repeatable list of simple list of length, percentage, or calc</li><li><a href="mask-clip"><code>mask-clip</code></a>: discrete</li><li><a href="mask-origin"><code>mask-origin</code></a>: discrete</li><li><a href="mask-size"><code>mask-size</code></a>: repeatable list of simple list of length, percentage, or calc</li><li><a href="mask-composite"><code>mask-composite</code></a>: discrete</li></ul></td></tr><tr class="odd"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    <mask-layer>#where
    <mask-layer> = <mask-reference> || <position> [ / <bg-size> ]? || <repeat-style> || <geometry-box> || [ <geometry-box> | no-clip ] || <compositing-operator> || <masking-mode>where
    <mask-reference> = none | <image> | <mask-source>
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]
    <bg-size> = [ <length-percentage> | auto ]{1,2} | cover | contain
    <repeat-style> = repeat-x | repeat-y | [ repeat | space | round | no-repeat ]{1,2}
    <geometry-box> = <shape-box> | fill-box | stroke-box | view-box
    <compositing-operator> = add | subtract | intersect | exclude
    <masking-mode> = alpha | luminance | match-sourcewhere
    <image> = <url> | <image()> | <image-set()> | <element()> | <paint()> | <cross-fade()> | <gradient>
    <mask-source> = <url>
    <length-percentage> = <length> | <percentage>
    <shape-box> = <box> | margin-boxwhere
    <image()> = image( <image-tags>? [ <image-src>? , <color>? ]! )
    <image-set()> = image-set( <image-set-option># )
    <element()> = element( <id-selector> )
    <paint()> = paint( <ident>, <declaration-value>? )
    <cross-fade()> = cross-fade( <cf-mixing-image> , <cf-final-image>? )
    <gradient> = <linear-gradient()> | <repeating-linear-gradient()> | <radial-gradient()> | <repeating-radial-gradient()> | <conic-gradient()>
    <box> = border-box | padding-box | content-boxwhere
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
    <angular-color-stop-list> = [ <angular-color-stop> [, <angular-color-hint>]? ]# , <angular-color-stop>where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>
    <linear-color-stop> = <color> <color-stop-length>?
    <linear-color-hint> = <length-percentage>
    <angular-color-stop> = <color> && <color-stop-angle>?
    <angular-color-hint> = <angle-percentage>where
    <color-stop-length> = <length-percentage>{1,2}
    <color-stop-angle> = <angle-percentage>{1,2}
    <angle-percentage> = <angle> | <percentage>

## Examples

### Masking an image

    .target {
      mask: url(#c1) luminance;
    }

    .anothertarget {
      mask: url(resources.svg#c1) 50px 30px/10px 10px repeat-x exclude;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/css-masking-1/#the-mask">CSS Masking Module Level 1<br />
<span class="small">The definition of 'mask' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Extends its usage to HTML elements.<br />
Extends its syntax by making it a shorthand for the new <code>mask-*</code> properties defined in that specification.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/masking.html#MaskProperty">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'mask' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`mask`

1

While the property is recognized, values applied to it don't have any effect.

1

The prefixed property can be used with SVG and HTML with a slightly different syntax, which allows setting the non-standard [`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment) property.

12

2

From Firefox 10, the default color space when handling masks is sRGB. Previously, the default and only supported color space was linear RGB. This changes the appearance of mask effects, but brings Firefox into compliance with the second edition of the SVG 1.1 specification.

No

15

While the property is recognized, values applied to it don't have any effect.

15

The prefixed property can be used with SVG and HTML with a slightly different syntax, which allows setting the non-standard [`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment) property.

3.2

While the property is recognized, values applied to it don't have any effect.

3.2

The prefixed property can be used with SVG and HTML with a slightly different syntax, which allows setting the non-standard [`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment) property.

2

While the property is recognized, values applied to it don't have any effect.

2

The prefixed property can be used with SVG and HTML with a slightly different syntax, which allows setting the non-standard [`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment) property.

18

While the property is recognized, values applied to it don't have any effect.

18

The prefixed property can be used with SVG and HTML with a slightly different syntax, which allows setting the non-standard [`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment) property.

4

From Firefox 10, the default color space when handling masks is sRGB. Previously, the default and only supported color space was linear RGB. This changes the appearance of mask effects, but brings Firefox into compliance with the second edition of the SVG 1.1 specification.

14

While the property is recognized, values applied to it don't have any effect.

14

The prefixed property can be used with SVG and HTML with a slightly different syntax, which allows setting the non-standard [`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment) property.

3.2

While the property is recognized, values applied to it don't have any effect.

3.2

The prefixed property can be used with SVG and HTML with a slightly different syntax, which allows setting the non-standard [`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment) property.

1.0

While the property is recognized, values applied to it don't have any effect.

1.0

The prefixed property can be used with SVG and HTML with a slightly different syntax, which allows setting the non-standard [`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment) property.

## See also

- [`clip-path`](clip-path), [`filter`](filter)
- [CSS Shapes, clipping and masking – and how to use them](https://hacks.mozilla.org/2017/06/css-shapes-clipping-and-masking/)
- [Applying SVG effects to HTML content](https://developer.mozilla.org/en-US/docs/Web/SVG/Applying_SVG_effects_to_HTML_content)
- [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mask" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mask</a>

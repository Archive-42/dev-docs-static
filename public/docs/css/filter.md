# filter

The `filter` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property applies graphical effects like blur or color shift to an element. Filters are commonly used to adjust the rendering of images, backgrounds, and borders.

Included in the CSS standard are several functions that achieve predefined effects. You can also reference an SVG filter with a URL to an [SVG filter element](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter).

## Syntax

    /* URL to SVG filter */
    filter: url("filters.svg#filter-id");

    /* <filter-function> values */
    filter: blur(5px);
    filter: brightness(0.4);
    filter: contrast(200%);
    filter: drop-shadow(16px 16px 20px blue);
    filter: grayscale(50%);
    filter: hue-rotate(90deg);
    filter: invert(75%);
    filter: opacity(25%);
    filter: saturate(30%);
    filter: sepia(60%);

    /* Multiple filters */
    filter: contrast(175%) brightness(3%);

    /* Use no filter */
    filter: none;

    /* Global values */
    filter: inherit;
    filter: initial;
    filter: unset;

With a function, use the following:

    filter: <filter-function> [<filter-function>]* | none

For a reference to an SVG [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) element, use the following:

    filter: url(file.svg#filter-element-id)

### Interpolation

If both the beginning and end filters have a function list of the same length without [`url()`](<url()>), each of their filter functions is interpolated according to its specific rules. If they have different lengths, the missing equivalent filter functions from the longer list are added to the end of the shorter list using their lacuna values, then all filter functions are interpolated according to their specific rules. If one filter is `none`, it is replaced with the filter functions list of the other one using the filter function default values, then all filter functions are interpolated according to their specific rules. Otherwise, discrete interpolation is used.

## Functions

The `filter` property is specified as `none` or one or more of the functions listed below. If the parameter for any function is invalid, the function returns `none`. Except where noted, the functions that take a value expressed with a percent sign (as in `34%`) also accept the value expressed as decimal (as in `0.34`).

When a single `filter` property has two or more functions it's results will be different from when two or more `filter` properties are separately applied with the same functions.

### SVG filter

#### url()

Takes an URI pointing to an [SVG filter](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter), which may be embedded in an external XML file.

    filter: url(resources.svg#c1)

### Filter functions

#### blur()

The [`blur()`](<filter-function/blur()>) function applies a Gaussian blur to the input image. The value of `radius` defines the value of the standard deviation to the Gaussian function, or how many pixels on the screen blend into each other, so a larger value will create more blur. The lacuna value for interpolation is `0`. The parameter is specified as a CSS length, but does not accept percentage values.

    filter: blur(5px)

    <svg style="position: absolute; top: -99999px" xmlns="http://www.w3.org/2000/svg">
      <filter id="svgBlur" x="-5%" y="-5%" width="110%" height="110%">
        <feGaussianBlur in="SourceGraphic" stdDeviation="5"/>
      </filter>
    </svg>

#### brightness()

The [`brightness()`](<filter-function/brightness()>) function applies a linear multiplier to the input image, making it appear more or less bright. A value of `0%` will create an image that is completely black. A value of `100%` leaves the input unchanged. Other values are linear multipliers on the effect. Values of an amount over `100%` are allowed, providing brighter results. The lacuna value for interpolation is `1`.

    filter: brightness(2)

    <svg style="position: absolute; top: -99999px" xmlns="http://www.w3.org/2000/svg">
      <filter id="brightness">
        <feComponentTransfer>
          <feFuncR type="linear" slope="[amount]"/>
          <feFuncG type="linear" slope="[amount]"/>
          <feFuncB type="linear" slope="[amount]"/>
        </feComponentTransfer>
      </filter>
    </svg>

#### contrast()

The [`contrast()`](<filter-function/contrast()>) function adjusts the contrast of the input image. A value of `0%` will create an image that is completely gray. A value of `100%` leaves the input unchanged. Values of an amount over `100%` are allowed, providing results with more contrast. The lacuna value for interpolation is `1`.

    filter: contrast(200%)

    <svg style="position: absolute; top: -99999px" xmlns="http://www.w3.org/2000/svg">
      <filter id="contrast">
        <feComponentTransfer>
          <feFuncR type="linear" slope="[amount]" intercept="-(0.5 * [amount]) + 0.5"/>
          <feFuncG type="linear" slope="[amount]" intercept="-(0.5 * [amount]) + 0.5"/>
          <feFuncB type="linear" slope="[amount]" intercept="-(0.5 * [amount]) + 0.5"/>
        </feComponentTransfer>
      </filter>
    </svg>

#### drop-shadow()

The [`drop-shadow()`](<filter-function/drop-shadow()>) function applies a drop shadow effect to the input image. A drop shadow is effectively a blurred, offset version of the input image's alpha mask drawn in a particular color, composited below the image. The function accepts a parameter of type `<shadow>` (defined in [CSS3 Backgrounds](https://www.w3.org/TR/css-backgrounds-3/#typedef-shadow)), with the exception that the `inset` keyword and `spread `parameter are not allowed. This function is similar to the more established [`box-shadow`](box-shadow) property; the difference is that with filters, some browsers provide hardware acceleration for better performance. The parameters of the `<shadow>` parameter are as follows:

`<offset-x>` `<offset-y>` <span class="small">(required)</span>  
These are two [`<length>`](length) values to set the shadow offset. `<offset-x>` specifies the horizontal distance. Negative values place the shadow to the left of the element. `<offset-y>` specifies the vertical distance. Negative values place the shadow above the element. See [`<length>`](length) for possible units.  
If both values are `0`, the shadow is placed behind the element (and may generate a blur effect if `<blur-radius>` and/or `<spread-radius>` is set).

`<blur-radius>` <span class="small">(optional)</span>  
This is a third [`<length>`](length) value. The larger this value, the bigger the blur, so the shadow becomes bigger and lighter. Negative values are not allowed. If not specified, it will be `0` (the shadow's edge is sharp).

`<color>` <span class="small">(optional)</span>  
See [`<color>`](color_value) values for possible keywords and notations. If not specified, the color used depends on the browser - it is usually the value of the [`<color>`](color_value) property, but note that Safari currently paints a transparent shadow in this case.

<!-- -->

    filter: drop-shadow(16px 16px 10px black)

    <svg style="position: absolute; top: -999999px" xmlns="http://www.w3.org/2000/svg">
     <filter id="drop-shadow">
        <feGaussianBlur in="SourceAlpha" stdDeviation="[radius]"/>
        <feOffset dx="[offset-x]" dy="[offset-y]" result="offsetblur"/>
        <feFlood flood-color="[color]"/>
        <feComposite in2="offsetblur" operator="in"/>
        <feMerge>
          <feMergeNode/>
          <feMergeNode in="SourceGraphic"/>
        </feMerge>
      </filter>
    </svg>

#### grayscale()

The [`grayscale()`](<filter-function/grayscale()>) function converts the input image to grayscale. The value of `amount` defines the proportion of the conversion. A value of `100%` is completely grayscale. A value of `0%` leaves the input unchanged. Values between `0%` and `100%` are linear multipliers on the effect. The lacuna value for interpolation is `0`.

    filter: grayscale(100%)

#### hue-rotate()

The [`hue-rotate()`](<filter-function/hue-rotate()>) function applies a hue rotation on the input image. The value of `angle` defines the number of degrees around the color circle the input samples will be adjusted. A value of `0deg` leaves the input unchanged. The lacuna value for interpolation is `0`. Though there is no maximum value; the effect of values above `360deg` wraps around.

    filter: hue-rotate(90deg)

    <svg style="position: absolute; top: -999999px" xmlns="http://www.w3.org/2000/svg">
      <filter id="svgHueRotate">
        <feColorMatrix type="hueRotate" values="[angle]"/>
      </filter>
    </svg>

#### invert()

The [`invert()`](<filter-function/invert()>) function inverts the samples in the input image. The value of `amount` defines the proportion of the conversion. A value of `100%` is completely inverted. A value of `0%` leaves the input unchanged. Values between `0%` and `100%` are linear multipliers on the effect. The lacuna value for interpolation is `0`.

    filter: invert(100%)

#### opacity()

The [`opacity()`](<filter-function/opacity()>) function applies transparency to the samples in the input image. The value of `amount` defines the proportion of the conversion. A value of `0%` is completely transparent. A value of `100%` leaves the input unchanged. Values between `0%` and `100%` are linear multipliers on the effect. This is equivalent to multiplying the input image samples by amount. The lacuna value for interpolation is `1`. This function is similar to the more established [`opacity`](opacity) property; the difference is that with filters, some browsers provide hardware acceleration for better performance.

    filter: opacity(50%)

#### saturate()

The [`saturate()`](<filter-function/saturate()>) function saturates the input image. The value of `amount` defines the proportion of the conversion. A value of `0%` is completely un-saturated. A value of `100%` leaves the input unchanged. Other values are linear multipliers on the effect. Values of amount over `100%` are allowed, providing super-saturated results. The lacuna value for interpolation is `1`.

    filter: saturate(200%)

#### sepia()

The [`sepia()`](<filter-function/sepia()>) function converts the input image to sepia. The value of `amount` defines the proportion of the conversion. A value of `100%` is completely sepia. A value of `0%` leaves the input unchanged. Values between `0%` and `100%` are linear multipliers on the effect. The lacuna value for interpolation is `0`.

    filter: sepia(100%)

## Combining functions

You may combine any number of functions to manipulate the rendering. The following example enhances the contrast and brightness of the image:

    filter: contrast(175%) brightness(103%)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements; In SVG, it applies to container elements excluding the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs"><code>defs</code></a> element and all graphics elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="#Interpolation">filter function list</a></td></tr></tbody></table>

## Formal syntax

    none | <filter-function-list>where
    <filter-function-list> = [ <filter-function> | <url> ]+where
    <filter-function> = <blur()> | <brightness()> | <contrast()> | <drop-shadow()> | <grayscale()> | <hue-rotate()> | <invert()> | <opacity()> | <saturate()> | <sepia()>where
    <blur()> = blur( <length> )
    <brightness()> = brightness( <number-percentage> )
    <contrast()> = contrast( [ <number-percentage> ] )
    <drop-shadow()> = drop-shadow( <length>{2,3} <color>? )
    <grayscale()> = grayscale( <number-percentage> )
    <hue-rotate()> = hue-rotate( <angle> )
    <invert()> = invert( <number-percentage> )
    <opacity()> = opacity( [ <number-percentage> ] )
    <saturate()> = saturate( <number-percentage> )
    <sepia()> = sepia( <number-percentage> )where
    <number-percentage> = <number> | <percentage>
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Applying filter functions

Examples of using the predefined functions are shown below. See each function for a specific example.

    .mydiv {
      filter: grayscale(50%);
    }

    /* Gray all images by 50% and blur by 10px */
    img {
      filter: grayscale(0.5) blur(10px);
    }

### Applying SVG filters

Examples of using the URL function with an SVG resource are as follows:

    .target {
      filter: url(#c1);
    }

    .mydiv {
      filter: url(commonfilters.xml#large-blur);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#FilterProperty">Filter Effects Module Level 1<br />
<span class="small">The definition of 'filter' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`filter`

53

18

In Chrome 18 to 19, the `saturate()` function only takes integers instead of decimal or percentage values. From Chrome 20, this bug is fixed.

12

12

35

49

No

Internet Explorer 4 to 9 implemented a non-standard `filter` property. The syntax was completely different from this one and is not documented here.

40

15

9.1

6

53

4.4

53

35

49

41

14

9.3

6

6.0

`svg`

No

No

35

No

No

No

No

No

35

No

No

No

## See also

- <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Applying_SVG_effects_to_HTML_content" class="internal">Applying SVG effects to HTML content</a>
- The [`mask`](mask) property
- <a href="https://developer.mozilla.org/en-US/docs/Web/SVG" class="internal">SVG</a>
- [Understanding CSS filters](https://www.html5rocks.com/en/tutorials/filters/understanding-css/), HTML5Rocks! article

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/filter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/filter</a>

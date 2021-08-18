# background

The `background` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets all background style properties at once, such as color, image, origin and size, or repeat method.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`background-attachment`](background-attachment)
- [`background-clip`](background-clip)
- [`background-color`](background-color)
- [`background-image`](background-image)
- [`background-origin`](background-origin)
- [`background-position`](background-position)
- [`background-repeat`](background-repeat)
- [`background-size`](background-size)

## Syntax

    /* Using a <background-color> */
    background: green;

    /* Using a <bg-image> and <repeat-style> */
    background: url("test.jpg") repeat-y;

    /* Using a <box> and <background-color> */
    background: border-box red;

    /* A single image, centered and scaled */
    background: no-repeat center/80% url("../img/image.png");

The `background` property is specified as one or more background layers, separated by commas.

The syntax of each layer is as follows:

- Each layer may include zero or one occurrences of any of the following values:
  - `<attachment>`
  - `<bg-image>`
  - `<position>`
  - `<bg-size>`
  - `<repeat-style>`
- The `<bg-size>` value may only be included immediately after `<position>`, separated with the '/' character, like this: "`center/80%`".
- The `<box>` value may be included zero, one, or two times. If included once, it sets both [`background-origin`](background-origin) and [`background-clip`](background-clip). If it is included twice, the first occurrence sets [`background-origin`](background-origin), and the second sets [`background-clip`](background-clip).
- The `<background-color>` value may only be included in the last layer specified.

### Values

`<attachment>`  
See [`background-attachment`](background-attachment)

`<box>`  
See [`background-clip`](background-clip) and [`background-origin`](background-origin)

`<background-color>`  
See [`background-color`](background-color)

`<bg-image>`  
See [`background-image`](background-image)

`<position>`  
See [`background-position`](background-position)

`<repeat-style>`  
See [`background-repeat`](background-repeat)

`<bg-size>`  
See [`background-size`](background-size).

## Accessibility concerns

Browsers do not provide any special information on background images to assistive technology. This is important primarily for screen readers, as a screen reader will not announce its presence and therefore convey nothing to its users. If the image contains information critical to understanding the page's overall purpose, it is better to describe it semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%e2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="background-image"><code>background-image</code></a>: <code>none</code></li><li><a href="background-position"><code>background-position</code></a>: <code>0% 0%</code></li><li><a href="background-size"><code>background-size</code></a>: <code>auto auto</code></li><li><a href="background-repeat"><code>background-repeat</code></a>: <code>repeat</code></li><li><a href="background-origin"><code>background-origin</code></a>: <code>padding-box</code></li><li><a href="background-clip"><code>background-clip</code></a>: <code>border-box</code></li><li><a href="background-attachment"><code>background-attachment</code></a>: <code>scroll</code></li><li><a href="background-color"><code>background-color</code></a>: <code>transparent</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="background-position"><code>background-position</code></a>: refer to the size of the background positioning area minus size of background image; size refers to the width for horizontal offsets and to the height for vertical offsets</li><li><a href="background-size"><code>background-size</code></a>: relative to the background positioning area</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="background-image"><code>background-image</code></a>: as specified, but with <a href="url()"><code>url()</code></a> values made absolute</li><li><a href="background-position"><code>background-position</code></a>: as each of the properties of the shorthand:<br />
<ul><li><a href="background-position-x"><code>background-position-x</code></a>: A list, each item consisting of: an offset given as a combination of an absolute length and a percentage, plus an origin keyword</li><li><a href="background-position-y"><code>background-position-y</code></a>: A list, each item consisting of: an offset given as a combination of an absolute length and a percentage, plus an origin keyword</li></ul></li><li><a href="background-size"><code>background-size</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="background-repeat"><code>background-repeat</code></a>: a list, each item consisting of two keywords, one per dimension</li><li><a href="background-origin"><code>background-origin</code></a>: as specified</li><li><a href="background-clip"><code>background-clip</code></a>: as specified</li><li><a href="background-attachment"><code>background-attachment</code></a>: as specified</li><li><a href="background-color"><code>background-color</code></a>: computed color</li></ul></td></tr><tr class="even"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="background-color"><code>background-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="background-image"><code>background-image</code></a>: discrete</li><li><a href="background-clip"><code>background-clip</code></a>: discrete</li><li><a href="background-position"><code>background-position</code></a>: repeatable list of simple list of length, percentage, or calc</li><li><a href="background-size"><code>background-size</code></a>: repeatable list of simple list of length, percentage, or calc</li><li><a href="background-repeat"><code>background-repeat</code></a>: discrete</li><li><a href="background-attachment"><code>background-attachment</code></a>: discrete</li></ul></td></tr></tbody></table>

## Formal syntax

    [ <bg-layer> , ]* <final-bg-layer>where
    <bg-layer> = <bg-image> || <bg-position> [ / <bg-size> ]? || <repeat-style> || <attachment> || <box> || <box>
    <final-bg-layer> = <'background-color'> || <bg-image> || <bg-position> [ / <bg-size> ]? || <repeat-style> || <attachment> || <box> || <box>where
    <bg-image> = none | <image>
    <bg-position> = [ [ left | center | right | top | bottom | <length-percentage> ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ] | [ center | [ left | right ] <length-percentage>? ] && [ center | [ top | bottom ] <length-percentage>? ] ]
    <bg-size> = [ <length-percentage> | auto ]{1,2} | cover | contain
    <repeat-style> = repeat-x | repeat-y | [ repeat | space | round | no-repeat ]{1,2}
    <attachment> = scroll | fixed | local
    <box> = border-box | padding-box | content-boxwhere
    <image> = <url> | <image()> | <image-set()> | <element()> | <paint()> | <cross-fade()> | <gradient>
    <length-percentage> = <length> | <percentage>where
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
    <angular-color-stop> = <color> && <color-stop-angle>?
    <angular-color-hint> = <angle-percentage>where
    <color-stop-length> = <length-percentage>{1,2}
    <color-stop-angle> = <angle-percentage>{1,2}
    <angle-percentage> = <angle> | <percentage>

## Examples

### Setting backgrounds with color keywords and images

#### HTML

    <p class="topbanner">
      Starry sky<br/>
      Twinkle twinkle<br/>
      Starry sky
    </p>
    <p class="warning">Here is a paragraph<p>

#### CSS

    .warning {
      background: pink;
    }

    .topbanner {
      background: url("https://mdn.mozillademos.org/files/11983/starsolid.gif") #99f repeat-y fixed;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#the-background">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'background' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The shorthand property has been extended to support multiple backgrounds and the new <a href="background-size"><code>background-size</code></a>, <a href="background-origin"><code>background-origin</code></a> and <a href="background-clip"><code>background-clip</code></a> properties.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/colors.html#propdef-background">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'background' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant changes</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#background">CSS Level 1<br />
<span class="small">The definition of 'background' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`background`

1

12

1

4

3.5

1

2

18

4

10.1

1

1.0

`SVG_image_as_background`

1

12

4

9

9.5

3.1

≤37

18

4

10.1

1

1.0

`background-clip`

21

12

22

9

15

5.1

3

25

22

14

4

1.5

`background-origin`

21

12

22

9

15

5.1

3

25

22

14

4

1.5

`background-size`

21

12

9

9

21

5.1

3

25

18

14

4

1.5

`multiple_backgrounds`

1

12

3.6

9

10.5

1.3

2

18

4

14

1

1.0

## See also

- [`box-decoration-break`](box-decoration-break)
- [Using gradients](css_images/using_css_gradients)
- [Using multiple backgrounds](css_backgrounds_and_borders/using_multiple_backgrounds)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background</a>

# background-image

The `background-image` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets one or more background images on an element.

The background images are drawn on stacking context layers on top of each other. The first layer specified is drawn as if it is closest to the user.

The [borders](border) of the element are then drawn on top of them, and the [`background-color`](background-color) is drawn beneath them. How the images are drawn relative to the box and its borders is defined by the [`background-clip`](background-clip) and [`background-origin`](background-origin) CSS properties.

If a specified image cannot be drawn (for example, when the file denoted by the specified URI cannot be loaded), browsers handle it as they would a `none` value.

**Note:** Even if the images are opaque and the color won't be displayed in normal circumstances, web developers should always specify a [`background-color`](background-color). If the images cannot be loaded—for instance, when the network is down—the background color will be used as a fallback.

## Syntax

Each background image is specified either as the keyword `none` or as an [`<image>`](image) value.

To specify multiple background images, supply multiple values, separated by a comma:

    background-image:
      linear-gradient(to bottom, rgba(255,255,0,0.5), rgba(0,0,255,0.5)),
      url('https://mdn.mozillademos.org/files/7693/catfront.png');

### Values

`none`  
Is a keyword denoting the absence of images.

`<image>`  
Is an [`<image>`](image) denoting the image to display. There can be several of them, separated by commas, as [multiple backgrounds](css_backgrounds_and_borders/using_multiple_backgrounds) are supported.

## Accessibility concerns

Browsers do not provide any special information on background images to assistive technology. This is important primarily for screen readers, as a screen reader will not announce its presence and therefore convey nothing to its users. If the image contains information critical to understanding the page's overall purpose, it is better to describe it semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%e2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified, but with <a href="url()"><code>url()</code></a> values made absolute</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <bg-image>#where
    <bg-image> = none | <image>where
    <image> = <url> | <image()> | <image-set()> | <element()> | <paint()> | <cross-fade()> | <gradient>where
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

### Layering background images

Note that the star image is partially transparent and is layered over the cat image.

#### HTML

    <div>
      <p class="catsandstars">
        This paragraph is full of cats<br />and stars.
      </p>
      <p>This paragraph is not.</p>
      <p class="catsandstars">
        Here are more cats for you.<br />Look at them!
      </p>
      <p>And no more.</p>
    </div>

#### CSS

    p {
      font-size: 1.5em;
      color: #FE7F88;
      background-image: none;
      background-color: transparent;
    }

    div {
      background-image:
          url("https://mdn.mozillademos.org/files/6457/mdn_logo_only_color.png");
    }

    .catsandstars {
      background-image:
          url("https://mdn.mozillademos.org/files/11991/startransparent.gif"),
          url("https://mdn.mozillademos.org/files/7693/catfront.png");
      background-color: transparent;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-backgrounds-3/#background-image">CSS Backgrounds and Borders Module Level 3<br />
<span class="small">The definition of 'background-image' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>From CSS2 Revision 1, the property has been extended to support multiple backgrounds and any <a href="image"><code>&lt;image&gt;</code></a> CSS data type.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/colors.html#propdef-background-image">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'background-image' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>From CSS1, the way images with and without intrinsic dimensions are handled is now described.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#background-image">CSS Level 1<br />
<span class="small">The definition of 'background-image' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`background-image`

1

12

1

If the `browser.display.use_document_colors` user preference in `about:config` is set to `false`, background images will not be displayed.

4

3.5

1

≤37

18

4

If the `browser.display.use_document_colors` user preference in `about:config` is set to `false`, background images will not be displayed.

14

1

1.0

`element`

No

No

4

No

No

No

No

No

4

No

No

No

`gradients`

1

Some versions support only experimental gradients prefixed with `-webkit`.

12

3.6

Some versions support only experimental gradients prefixed with `-moz`.

10

11

Some versions support only experimental gradients prefixed with `-o`.

4

Some versions support only experimental gradients prefixed with `-webkit`.

≤37

Some versions support only experimental gradients prefixed with `-webkit`.

18

Some versions support only experimental gradients prefixed with `-webkit`.

4

Some versions support only experimental gradients prefixed with `-moz`.

14

Some versions support only experimental gradients prefixed with `-webkit`.

3.2

Some versions support only experimental gradients prefixed with `-webkit`.

1.0

Some versions support only experimental gradients prefixed with `-webkit`.

`image-rect`

No

No

4

No

No

No

No

No

4

No

No

No

`image-set`

21

79

No

See [bug 1107646](https://bugzil.la/1107646).

No

15

6

Support for `url` images only and `x` is the only supported resolution unit. See [bug 160934](https://webkit.org/b/160934).

4.4

25

No

See [bug 1107646](https://bugzil.la/1107646).

14

6

Support for `url` images only and `x` is the only supported resolution unit. See [bug 160934](https://webkit.org/b/160934).

1.5

`multiple_backgrounds`

1

12

3.6

9

10.5

1.3

≤37

18

4

14

1

1.0

`svg_images`

8

12

4

9

9.5

5

Support of SVG in CSS background is incomplete.

≤37

18

4

14

5

Support of SVG in CSS background is incomplete.

1.0

## See also

- [Implementing image sprites in CSS](css_images/implementing_image_sprites_in_css)
- [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)
- Image-related data types: [`<image>`](image), [`<gradient>`](gradient)
- Image-related functions:
  - [`cross-fade()`](<cross-fade()>)
  - [`element()`](<element()>)
  - [`image()`](<image()>)
  - [`image-set()`](<image-set()>)
  - [`linear-gradient()`](<linear-gradient()>)
  - [`radial-gradient()`](<radial-gradient()>)
  - [`repeating-linear-gradient()`](<repeating-linear-gradient()>)
  - [`repeating-radial-gradient()`](<repeating-radial-gradient()>)
  - [`paint()`](<paint()>)
  - [`url()`](<url()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/background-image" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/background-image</a>

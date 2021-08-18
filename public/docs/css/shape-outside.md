# shape-outside

The `shape-outside` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines a shape—which may be non-rectangular—around which adjacent inline content should wrap. By default, inline content wraps around its margin box; `shape-outside` provides a way to customize this wrapping, making it possible to wrap text around complex objects rather than simple boxes.

## Syntax

    /* Keyword values */
    shape-outside: none;
    shape-outside: margin-box;
    shape-outside: content-box;
    shape-outside: border-box;
    shape-outside: padding-box;

    /* Function values */
    shape-outside: circle();
    shape-outside: ellipse();
    shape-outside: inset(10px 10px 10px 10px);
    shape-outside: polygon(10px 10px, 20px 20px, 30px 30px);
    shape-outside: path('M0.5,1 C0.5,1,0,0.7,0,0.3 A0.25,0.25,1,1,1,0.5,0.3 A0.25,0.25,1,1,1,1,0.3 C1,0.7,0.5,1,0.5,1 Z');

    /* <url> value */
    shape-outside: url(image.png);

    /* <gradient> value */
    shape-outside: linear-gradient(45deg, rgba(255, 255, 255, 0) 150px, red 150px);

    /* Global values */
    shape-outside: initial;
    shape-outside: inherit;
    shape-outside: unset;

The `shape-outside` property is specified using the values from the list below, which define the _float area_ for _float elements_. The float area determines the shape around which inline content (float elements) wrap.

### Values

`none`  
The float area is unaffected. Inline content wraps around the element's margin box, like usual.

`<shape-box>`  
The float area is computed according to the shape of a float element's edges (as defined by the [CSS box model](css_box_model/introduction_to_the_css_box_model)). This can be `margin-box`, `border-box`, `padding-box`, or `content-box`. The shape includes any curvature created by the [`border-radius`](border-radius) property (behavior which is similar to [`background-clip`](background-clip)).

`margin-box`  
<span style="line-height: 1.5;">Defines the shape enclosed by the outside margin edge. The corner radii of this shape are determined by the corresponding [`border-radius`](border-radius) and [`margin`](margin) values. If the `border-radius / margin` </span>ratio is `1` or more, then the margin box corner radius is `border-radius + margin`. If the ratio is less than `1`, then the margin box corner radius is `border-radius + (margin * (1 + (ratio-1)^3))`.

`border-box`  
Defines the shape enclosed by the outside border edge. The shape follows the normal border radius shaping rules for the outside of the border.

`padding-box`  
Defines the shape enclosed by the outside padding edge. The shape follows the normal border radius shaping rules for the inside of the border.

`content-box`  
Defines the shape enclosed by the outside content edge. Each corner radius of this box is the larger of `0` or `border-radius - border-width - padding`.

[`<basic-shape>`](basic-shape)  
The float area is computed based on the shape created by of one of `inset()`, `circle()`, `ellipse()`, `polygon()`, or as added in the level 2 specification `path()`. If a `<shape-box>` is also supplied, it defines the reference box for the `<basic-shape>` function. Otherwise, the reference box defaults to `margin-box`.

[`<image>`](image)  
The float area is extracted and computed based on the alpha channel of the specified [`<image>`](image) as defined by [`shape-image-threshold`](shape-image-threshold).

**Note:** [User agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) must use the potentially CORS-enabled fetch method defined by the HTML5 specification for all URLs in a `shape-outside` value. When fetching, user agents must use "Anonymous" mode, set the referrer source to the stylesheet's URL, and set the origin to the URL of the containing document. If this results in network errors such that there is no valid fallback image, the effect is as if the value `none` had been specified.

## Interpolation

When animating between one `<basic-shape>` and a second, the rules below are applied. The values in the shape functions interpolate as a simple list. The list values interpolate as [`<length>`](length), [`<percentage>`](percentage), or [`calc()`](<calc()>) where possible. If list values are not one of those types but are identical (such as finding `nonzero` in the same list position in both lists), those values do interpolate.

- Both shapes must use the same reference box.
- If both shapes are the same type, that type is `ellipse()` or `circle()`, and none of the radii use the `closest-side` or `farthest-side` keywords, interpolate between each value in the shape functions.
- If both shapes are of type `inset()`, interpolate between each value in the shape functions.
- If both shapes are of type `polygon()`, both polygons have the same number of vertices, and use the same `<fill-rule>`, interpolate between each value in the shape functions.
- In all other cases no interpolation occurs.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>floats</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as defined for <a href="basic-shape"><code>&lt;basic-shape&gt;</code></a> (with <a href="shape-outside"><code>shape-box</code></a> following, if supplied), the <a href="image"><code>&lt;image&gt;</code></a> with its URI made absolute, otherwise as specified.</td></tr><tr class="odd"><td>Animation type</td><td>yes, as specified for <a href="basic-shape"><code>&lt;basic-shape&gt;</code></a>, otherwise no</td></tr></tbody></table>

## Formal syntax

    none | [ <shape-box> || <basic-shape> ] | <image>where
    <shape-box> = <box> | margin-box
    <basic-shape> = <inset()> | <circle()> | <ellipse()> | <polygon()> | <path()>
    <image> = <url> | <image()> | <image-set()> | <element()> | <paint()> | <cross-fade()> | <gradient>where
    <box> = border-box | padding-box | content-box
    <inset()> = inset( <length-percentage>{1,4} [ round <'border-radius'> ]? )
    <circle()> = circle( [ <shape-radius> ]? [ at <position> ]? )
    <ellipse()> = ellipse( [ <shape-radius>{2} ]? [ at <position> ]? )
    <polygon()> = polygon( <fill-rule>? , [ <length-percentage> <length-percentage> ]# )
    <path()> = path( [ <fill-rule>, ]? <string> )
    <image()> = image( <image-tags>? [ <image-src>? , <color>? ]! )
    <image-set()> = image-set( <image-set-option># )
    <element()> = element( <id-selector> )
    <paint()> = paint( <ident>, <declaration-value>? )
    <cross-fade()> = cross-fade( <cf-mixing-image> , <cf-final-image>? )
    <gradient> = <linear-gradient()> | <repeating-linear-gradient()> | <radial-gradient()> | <repeating-radial-gradient()> | <conic-gradient()>where
    <length-percentage> = <length> | <percentage>
    <shape-radius> = <length-percentage> | closest-side | farthest-side
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]
    <fill-rule> = nonzero | evenodd
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

### Funneling text

#### HTML

    <div class="main">
      <div class="left"></div>
      <div class="right"></div>
      <p>
        Sometimes a web page's text content appears to be
        funneling your attention towards a spot on the page
        to drive you to follow a particular link. Sometimes
        you don't notice.
      </p>
    </div>

#### CSS

    .main {
      width: 530px;
    }

    .left,
    .right {
      width: 40%;
      height: 12ex;
      background-color: lightgray;
    }

    .left {
      -webkit-shape-outside: polygon(0 0, 100% 100%, 0 100%);
      shape-outside: polygon(0 0, 100% 100%, 0 100%);
      float: left;
      -webkit-clip-path: polygon(0 0, 100% 100%, 0 100%);
      clip-path: polygon(0 0, 100% 100%, 0 100%);
    }

    .right {
      -webkit-shape-outside: polygon(100% 0, 100% 100%, 0 100%);
      shape-outside: polygon(100% 0, 100% 100%, 0 100%);
      float: right;
      -webkit-clip-path: polygon(100% 0, 100% 100%, 0 100%);
      clip-path: polygon(100% 0, 100% 100%, 0 100%);
    }

    p {
      text-align: center;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-shapes/#shape-outside-property">CSS Shapes Module Level 1<br />
<span class="small">The definition of 'shape-outside' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-shapes-2/#shape-outside-property">CSS Shapes Module Level 2<br />
<span class="small">The definition of 'shape-outside' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds the <code>path()</code> value</td></tr></tbody></table>

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

`shape-outside`

37

79

62

61-62

No

24

10.1

37

37

62

61-62

24

10.3

3.0

`circle`

37

79

62

61-62

No

24

10.1

37

37

62

61-62

24

10.3

3.0

`gradient`

37

79

62

61-62

No

24

10.1

37

37

62

61-62

24

10.3

3.0

`image`

37

79

62

61-62

No

24

10.1

37

37

62

61-62

24

10.3

3.0

`inset`

37

79

62

61-62

No

24

10.1

37

37

62

61-62

24

10.3

3.0

`polygon`

37

79

62

61-62

No

24

10.1

37

37

62

61-62

24

10.3

3.0

`three_value_syntax`

37-68

No

62-70

61-62

No

24-55

10.1

37-68

37-68

62

61-62

24-48

10.3

3.0-10.0

## See also

- [CSS Shapes](css_shapes)
- [Overview of CSS Shapes](css_shapes/overview_of_css_shapes)
- [Shapes from Box Values](css_shapes/from_box_values)
- [Basic Shapes](css_shapes/basic_shapes)
- [Shapes from Images](css_shapes/shapes_from_images)
- [`<basic-shape>`](basic-shape)
- [`shape-margin`](shape-margin)
- [`shape-image-threshold`](shape-image-threshold)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside</a>

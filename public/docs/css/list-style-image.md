# list-style-image

The `list-style-image` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets an image to be used as the list item marker.

It is often more convenient to use the shorthand [`list-style`](list-style).

**Note:** This property is applied to list items, i.e. elements with `display`: list-item; [by default](https://www.w3.org/TR/html5/rendering.html#lists) this includes [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) elements. Because this property is inherited, it can be set on the parent element (normally [`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) or [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)) to let it apply to all list items.

## Syntax

    /* Keyword values */
    list-style-image: none;

    /* <url> values */
    list-style-image: url('starsolid.gif');

    /* valid image values */
    list-style-image: linear-gradient(to left bottom, red, blue);

    /* Global values */
    list-style-image: inherit;
    list-style-image: initial;
    list-style-image: unset;

### Values

[`<image>`](image)  
A valid image to use as the marker.

`none`  
Specifies that no image is used as the marker. If this value is set, the marker defined in [`list-style-type`](list-style-type) will be used instead.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>list items</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <image> | nonewhere
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

### Using a url value

#### HTML

    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
    </ul>

#### CSS

    ul {
      list-style-image: url("https://mdn.mozillademos.org/files/11981/starsolid.gif");
    }

#### Result

### Using a gradient

#### HTML

    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
    </ul>

#### CSS

    ul {
      font-size: 200%;
      list-style-image: linear-gradient(to left bottom, red, blue);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-lists-3/#propdef-list-style-image">CSS Lists Module Level 3<br />
<span class="small">The definition of 'list-style-image' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Extends support to any <a href="image"><code>&lt;image&gt;</code></a> data type.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/generate.html#propdef-list-style-image">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'list-style-image' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`list-style-image`

1

12

1

Before Firefox 86, this property did not accept an `<image>` type, and required the URL of an image.

4

7

1

1

18

4

Before Firefox 86, this property did not accept an `<image>` type, and required the URL of an image.

10.1

1

1.0

## See also

- [`list-style`](list-style), [`list-style-type`](list-style-type), [`list-style-position`](list-style-position)
- [`url()`](<url()>) function

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image</a>

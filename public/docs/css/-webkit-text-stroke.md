# -webkit-text-stroke

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `-webkit-text-stroke` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the [width](length) and [color](color_value) of strokes for text characters. This is a shorthand property for the longhand properties [`-webkit-text-stroke-width`](-webkit-text-stroke-width) and [`-webkit-text-stroke-color`](-webkit-text-stroke-color).

    /* Width and color values */
    -webkit-text-stroke: 4px navy;
    text-stroke: 4px navy;

    /* Global values */
    -webkit-text-stroke: inherit;
    -webkit-text-stroke: initial;
    -webkit-text-stroke: unset;
    text-stroke: inherit;
    text-stroke: initial;
    text-stroke: unset;

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`-webkit-stroke-color`](-webkit-text-stroke-color)
- [`-webkit-stroke-width`](-webkit-text-stroke-width)

## Syntax

### Values

[`<length>`](length)  
The width of the stroke.

[`<color>`](color_value)  
The color of the stroke.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="-webkit-text-stroke-width"><code>-webkit-text-stroke-width</code></a>: <code>0</code></li><li><a href="-webkit-text-stroke-color"><code>-webkit-text-stroke-color</code></a>: <code>currentcolor</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="-webkit-text-stroke-width"><code>-webkit-text-stroke-width</code></a>: absolute <a href="length"><code>&lt;length&gt;</code></a></li><li><a href="-webkit-text-stroke-color"><code>-webkit-text-stroke-color</code></a>: computed color</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="-webkit-text-stroke-width"><code>-webkit-text-stroke-width</code></a>: discrete</li><li><a href="-webkit-text-stroke-color"><code>-webkit-text-stroke-color</code></a>: a <a href="color_value#interpolation">color</a></li></ul></td></tr></tbody></table>

## Formal syntax

    <length> || <color>where
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Adding a red text stroke

#### HTML

    <p id="example">The stroke of this text is red.</p>

#### CSS

    #example {
      font-size: 3em;
      margin: 0;
      -webkit-text-stroke: 2px red;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://compat.spec.whatwg.org/#the-webkit-text-stroke">Compatibility Standard<br />
<span class="small">The definition of '-webkit-text-stroke' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial standardization</td></tr><tr class="even"><td><a href="https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariCSSRef/Articles/StandardCSSProperties.html#//apple_ref/doc/uid/TP30001266-_webkit_text_stroke">Safari CSS Reference<br />
<span class="small">'-webkit-text-stroke' in that document.</span></a></td><td>Non-standard unofficial documentation</td><td>Initial definition</td></tr></tbody></table>

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

`-webkit-text-stroke`

4

15

49

48

No

15

3

4

18

49

48

14

2

1.0

## See also

- [Surfin' Safari blog post announcing this feature](https://www.webkit.org/blog/85/introducing-text-stroke/)
- [CSS-Tricks article explaining this feature](https://css-tricks.com/adding-stroke-to-web-text/)
- [`-webkit-text-stroke-width`](-webkit-text-stroke-width)
- [`-webkit-text-stroke-color`](-webkit-text-stroke-color)
- [`-webkit-text-fill-color`](-webkit-text-fill-color)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke</a>

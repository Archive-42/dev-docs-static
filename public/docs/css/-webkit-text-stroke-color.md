# -webkit-text-stroke-color

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `-webkit-text-stroke-color` CSS property specifies the stroke [color](color_value) of characters of text. If this property is not set, the value of the [`color`](color) property is used.

    /* <color> values */
    -webkit-text-stroke-color: red;
    -webkit-text-stroke-color: #e08ab4;
    -webkit-text-stroke-color: rgb(200, 100, 0);

    /* Global values */
    -webkit-text-stroke-color: inherit;
    -webkit-text-stroke-color: initial;
    -webkit-text-stroke-color: unset;

## Syntax

### Values

`<color>`  
The color of the stroke.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>currentcolor</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>computed color</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="color_value#interpolation">color</a></td></tr></tbody></table>

## Formal syntax

    <color>where
    <color> = <rgb()> | <rgba()> | <hsl()> | <hsla()> | <hex-color> | <named-color> | currentcolor | <deprecated-system-color>where
    <rgb()> = rgb( <percentage>{3} [ / <alpha-value> ]? ) | rgb( <number>{3} [ / <alpha-value> ]? ) | rgb( <percentage>#{3} , <alpha-value>? ) | rgb( <number>#{3} , <alpha-value>? )
    <rgba()> = rgba( <percentage>{3} [ / <alpha-value> ]? ) | rgba( <number>{3} [ / <alpha-value> ]? ) | rgba( <percentage>#{3} , <alpha-value>? ) | rgba( <number>#{3} , <alpha-value>? )
    <hsl()> = hsl( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsl( <hue>, <percentage>, <percentage>, <alpha-value>? )
    <hsla()> = hsla( <hue> <percentage> <percentage> [ / <alpha-value> ]? ) | hsla( <hue>, <percentage>, <percentage>, <alpha-value>? )where
    <alpha-value> = <number> | <percentage>
    <hue> = <number> | <angle>

## Examples

### Varying the stroke color

#### HTML

    <p>Text with stroke</p>
    <input type="color" value="#ff0000">

#### CSS

    p {
      margin: 0;
      font-size: 4em;
      -webkit-text-stroke-width: 3px;
      -webkit-text-stroke-color: #ff0000; /* Can be changed in the live sample */
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://compat.spec.whatwg.org/#the-webkit-text-stroke-color">Compatibility Standard<br />
<span class="small">The definition of '-webkit-text-stroke-color' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial standardization</td></tr><tr class="even"><td><a href="https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariCSSRef/Articles/StandardCSSProperties.html#//apple_ref/doc/uid/TP30001266--webkit-text-stroke-color">Safari CSS Reference<br />
<span class="small">'-webkit-text-stroke-color' in that document.</span></a></td><td>Non-standard unofficial documentation</td><td>Initial documentation</td></tr></tbody></table>

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

`-webkit-text-stroke-color`

1

15

49

48

No

15

3

37

18

49

48

15

2

1.0

## See also

- [Surfin' Safari blog post announcing this feature](https://www.webkit.org/blog/85/introducing-text-stroke/)
- [CSS-Tricks article explaining this feature](https://css-tricks.com/adding-stroke-to-web-text/)
- [`-webkit-text-fill-color`](-webkit-text-fill-color)
- [`-webkit-text-stroke-width`](-webkit-text-stroke-width)
- [`-webkit-text-stroke`](-webkit-text-stroke)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke-color" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-text-stroke-color</a>

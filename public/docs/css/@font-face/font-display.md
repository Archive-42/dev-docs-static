# font-display

The `font-display` descriptor determines how a font face is displayed based on whether and when it is downloaded and ready to use.

## Syntax

    /* Keyword values */
    font-display: auto;
    font-display: block;
    font-display: swap;
    font-display: fallback;
    font-display: optional;

### Values

`auto`  
The font display strategy is defined by the user agent.

`block`  
Gives the font face a short block period and an infinite swap period.

`swap`  
Gives the font face an extremely small block period and an infinite swap period.

`fallback`  
Gives the font face an extremely small block period and a short swap period.

`optional`  
Gives the font face an extremely small block period and no swap period.

**Note**

In Firefox, the preferences `gfx.downloadable_fonts.fallback_delay` and `gfx.downloadable_fonts.fallback_delay_short` provide the duration of the "short" and "extremely small" periods, respectively.

## Description

### The font display timeline

The font display timeline is based on a timer that begins the moment the user agent attempts to use a given downloaded font face. The timeline is divided into the three periods below which dictate the rendering behavior of any elements using the font face.

Font block period  
If the font face is not loaded, any element attempting to use it must render an _invisible_ fallback font face. If the font face successfully loads during this period, it is used normally.

Font swap period  
If the font face is not loaded, any element attempting to use it must render a fallback font face. If the font face successfully loads during this period, it is used normally.

Font failure period  
If the font face is not loaded, the user agent treats it as a failed load causing normal font fallback.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@font-face"><code>@font-face</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    [ auto | block | swap | fallback | optional ]

## Examples

### Specifying fallback font-display

    @font-face {
      font-family: ExampleFont;
      src: url(/path/to/fonts/examplefont.woff) format('woff'),
           url(/path/to/fonts/examplefont.eot) format('eot');
      font-weight: 400;
      font-style: normal;
      font-display: fallback;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-display-desc">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-display' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-display`

72

79

58

No

60

11.1

72

72

58

51

11.3

11.0

## See also

- [`font-family`](font-family)
- [`font-stretch`](font-stretch)
- [`font-style`](font-style)
- [`font-weight`](font-weight)
- [`font-variant`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`font-variation-settings`](font-variation-settings)
- [`src`](src)
- [`unicode-range`](unicode-range)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display</a>

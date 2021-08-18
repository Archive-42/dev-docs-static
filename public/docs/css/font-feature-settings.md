# font-feature-settings

The `font-feature-settings` CSS property controls advanced typographic features in OpenType fonts.

## Syntax

    /* Use the default settings */
    font-feature-settings: normal;

    /* Set values for OpenType feature tags */
    font-feature-settings: "smcp";
    font-feature-settings: "smcp" on;
    font-feature-settings: "swsh" 2;
    font-feature-settings: "smcp", "swsh" 2;

    /* Global values */
    font-feature-settings: inherit;
    font-feature-settings: initial;
    font-feature-settings: unset;

Whenever possible, Web authors should instead use the [`font-variant`](font-variant) shorthand property or an associated longhand property such as [`font-variant-ligatures`](font-variant-ligatures), [`font-variant-caps`](font-variant-caps), [`font-variant-east-asian`](font-variant-east-asian), [`font-variant-alternates`](font-variant-alternates), [`font-variant-numeric`](font-variant-numeric) or [`font-variant-position`](font-variant-position).

These lead to more effective, predictable, understandable results than `font-feature-settings`, which is a low-level feature designed to handle special cases where no other way exists to enable or access an OpenType font feature. In particular, `font-feature-settings` shouldn't be used to enable small caps.

### Values

`normal`  
Text is laid out using default settings.

`<feature-tag-value>`  
When rendering text, the list of OpenType feature tag value is passed to the text layout engine to enable or disable font features. The tag is always a [`<string>`](string) of 4 ASCII characters. If it has more or less characters, or if it contains characters outside the `U+20` – `U+7E` codepoint range, the whole property is invalid.  
The value is a positive integer. The two keywords `on` and `off` are synonyms for `1` and `0` respectively. If no value is set, the default is `1`. For non-Boolean OpenType features (e.g. [stylistic alternates](https://www.microsoft.com/typography/otspec/features_pt.htm#salt)), the value implies a particular glyph to be selected; for Boolean values, it is a switch.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | <feature-tag-value>#where
    <feature-tag-value> = <string> [ <integer> | on | off ]?

## Examples

### Enabling various font features

    /* use small-cap alternate glyphs */
    .smallcaps { font-feature-settings: "smcp" on; }

    /* convert both upper and lowercase to small caps (affects punctuation also) */
    .allsmallcaps { font-feature-settings: "c2sc", "smcp"; }

    /* use zeros with a slash through them to differentiate from "O" */

    .nicezero { font-feature-settings: "zero"; }

    /* enable historical forms */
    .hist { font-feature-settings: "hist"; }

    /* disable common ligatures, usually on by default */
    .noligs { font-feature-settings: "liga" 0; }

    /* enable tabular (monospaced) figures */
    td.tabular { font-feature-settings: "tnum"; }

    /* enable automatic fractions */
    .fractions { font-feature-settings: "frac"; }

    /* use the second available swash character */
    .swash { font-feature-settings: "swsh" 2; }

    /* enable stylistic set 7 */
    .fancystyle {
      font-family: Gabriola; /* available on Windows 7, and on Mac OS */
      font-feature-settings: "ss07";
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#propdef-font-feature-settings">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-feature-settings' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-feature-settings`

48

16

15

34

The [ISO/IEC CD 14496-22 3rd edition](http://mpeg.chiariglione.org/standards/mpeg-4/open-font-format/text-isoiec-cd-14496-22-3rd-edition) suggests using the `ssty` feature to provide glyph variants more suitable for use in scripts (for example primes used as superscripts). Starting with Firefox 29, this is done automatically by the [MathML](https://developer.mozilla.org/docs/Web/MathML) rendering engine. The ISO/IEC CD 14496-22 3rd edition also suggests applying the `dtls` feature to letters when placing mathematical accents to get dotless forms (for example dotless i, j with a hat). Starting with Firefox 35, this is done automatically by the MathML rendering engine. You can override the default values determined by the MathML rendering engine with CSS.

15

From Firefox 4 to Firefox 14 (inclusive), Firefox supported an older, slightly different syntax. See [OpenType Font Feature support in Firefox 4](http://hacks.mozilla.org/2010/11/firefox-4-font-feature-support/).

10

35

15

9.1

4-6

4.4

48

34

The [ISO/IEC CD 14496-22 3rd edition](http://mpeg.chiariglione.org/standards/mpeg-4/open-font-format/text-isoiec-cd-14496-22-3rd-edition) suggests using the `ssty` feature to provide glyph variants more suitable for use in scripts (for example primes used as superscripts). Starting with Firefox 29, this is done automatically by the [MathML](https://developer.mozilla.org/docs/Web/MathML) rendering engine. The ISO/IEC CD 14496-22 3rd edition also suggests applying the `dtls` feature to letters when placing mathematical accents to get dotless forms (for example dotless i, j with a hat). Starting with Firefox 35, this is done automatically by the MathML rendering engine. You can override the default values determined by the MathML rendering engine with CSS.

15

From Firefox 4 to Firefox 14 (inclusive), Firefox supported an older, slightly different syntax. See [OpenType Font Feature support in Firefox 4](http://hacks.mozilla.org/2010/11/firefox-4-font-feature-support/).

35

14

9.3

3.2-6.1

5.0

## See also

- [`font-display`](@font-face/font-display)
- [`font-family`](@font-face/font-family)
- [`font-stretch`](@font-face/font-stretch)
- [`font-style`](@font-face/font-style)
- [`font-weight`](@font-face/font-weight)
- [`font-variant`](@font-face/font-variant)
- [`font-variation-settings`](@font-face/font-variation-settings)
- [`src`](@font-face/src)
- [`unicode-range`](@font-face/unicode-range)
- [OpenType Feature Tags](https://www.microsoft.com/typography/otspec/featurelist.htm) list
- [Using the whole font](https://blogs.msdn.com/b/ie/archive/2012/01/09/css-corner-using-the-whole-font.aspx)  
  _(**Note:** The `-moz` syntax is the old one. On Gecko, use the `-ms` syntax but with `-moz`.)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-feature-settings" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-feature-settings</a>

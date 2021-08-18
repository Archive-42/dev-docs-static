# font-variation-settings

The `font-variation-settings` CSS descriptor allows authors to specify low-level OpenType or TrueType font variations in the [`@font-face`](../@font-face) rule.

## Syntax

    /* Use the default settings */
    font-variation-settings: normal;

    /* Set values for OpenType axis names */
    font-variation-settings: "xhgt" 0.7;

### Values

`normal`  
Text is laid out using default settings.

`<string> <number>`  
When rendering text, the list of OpenType axis names is passed to the text layout engine to enable or disable font features. Each setting is always a [`<string>`](../string) of 4 ASCII characters, followed by a [`<number>`](../number) indicating the axis value. If the `<string>` has more or fewer characters or contains characters outside the U+20 - U+7E codepoint range, the whole property is invalid. The `<number>` can be fractional or negative.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@font-face"><code>@font-face</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    normal | [ <string> <number> ]#

## Examples

### Setting font weight and stretch in a @font-face rule

    @font-face {
      font-family: 'OpenTypeFont';
      src: url('open_type_font.woff2') format('woff2');
      font-weight: normal;
      font-style: normal;
      font-variation-settings: 'wght' 400, 'wdth' 300;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-rend-desc">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-variation-settings' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-variation-settings`

62

79

62

No

49

No

62

62

62

46

No

8.0

## See also

- [`font-display`](font-display)
- [`font-family`](font-family)
- [`font-stretch`](font-stretch)
- [`font-style`](font-style)
- [`font-weight`](font-weight)
- [`font-variant`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`src`](src)
- [`unicode-range`](unicode-range)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-variation-settings" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-variation-settings</a>

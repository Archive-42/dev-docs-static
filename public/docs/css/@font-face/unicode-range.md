# unicode-range

The `unicode-range` CSS descriptor sets the specific range of characters to be used from a font defined by [`@font-face`](../@font-face) and made available for use on the current page. If the page doesn't use any character in this range, the font is not downloaded; if it uses at least one, the whole font is downloaded.

## Syntax

    /* <unicode-range> values */
    unicode-range: U+26;               /* single codepoint */
    unicode-range: U+0-7F;
    unicode-range: U+0025-00FF;        /* codepoint range */
    unicode-range: U+4??;              /* wildcard range */
    unicode-range: U+0025-00FF, U+4??; /* multiple values */

### Values

**_single codepoint_**  
A single Unicode character code point, for example `U+26`.

**_codepoint range_**  
A range of Unicode code points. So for example, `U+0025-00FF` means _include all characters in the range `U+0025` to `U+00FF`_.

**_wildcard range_**  
A range of Unicode code points containing wildcard characters, that is using the `'?'` character, so for example `U+4??` means _include all characters in the range `U+400` to `U+4FF`_.

## Description

The purpose of this descriptor is to allow the font resources to be segmented so that a browser only needs to download the font resource needed for the text content of a particular page. For example, a site with many localizations could provide separate font resources for English, Greek and Japanese. For users viewing the English version of a page, the font resources for Greek and Japanese fonts wouldn't need to be downloaded, saving bandwidth.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@font-face"><code>@font-face</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>U+0-10FFFF</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    <unicode-range>#

## Examples

### Using a different font for a single character

In this example we create a simple HTML containing a single [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element, including an ampersand, that we want to style with a different font. To make it obvious, we will use a sans-serif font, _Helvetica_, for the text, and a serif font, _Times New Roman_, for the ampersand.

In the CSS we are in effect defining a completely separate [`@font-face`](../@font-face) that only includes a single character in it, meaning that only this character will be styled with this font. We could also have done this by wrapping the ampersand in a [`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) and applying a different font just to that, but that is an extra element and rule set.

#### HTML

    <div>Me & You = Us</div>

#### CSS

    @font-face {
      font-family: 'Ampersand';
      src: local('Times New Roman');
      unicode-range: U+26;
    }

    div {
      font-size: 4em;
      font-family: Ampersand, Helvetica, sans-serif;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#unicode-range-desc">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'unicode-range' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`unicode-range`

1

12

36

9

15

3.2

≤37

18

36

14

3

1.0

## See also

- [`font-display`](font-display)
- [`font-family`](font-family)
- [`font-stretch`](font-stretch)
- [`font-style`](font-style)
- [`font-weight`](font-weight)
- [`font-variant`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`font-variation-settings`](font-variation-settings)
- [`src`](src)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range</a>

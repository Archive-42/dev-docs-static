# CSS Fonts

**CSS Fonts** is a module of CSS that defines font-related properties and how font resources are loaded. It lets you define the style of a font, such as its family, size and weight, line height, and the glyph variants to use when multiple are available for a single character.

## Basic example

The following example shows a simple use of basic font properties to style a paragraph of text.

    p {
      width: 600px;
      margin: 0 auto;
      font-family: "Helvetica Neue", "Arial", sans-serif;
      font-style: italic;
      font-weight: 100;
      font-variant-ligatures: normal;
      font-size: 2rem;
      letter-spacing: 1px;
    }

    <p>Three hundred years ago<br>
      I thought I might get some sleep<br>
      I stretched myself out onna antique bed<br>
      An' my spirit did a midnite creep</p>

The result is as follows:

## Variable fonts examples

You can find a number of variable fonts examples at [v-fonts.com](https://v-fonts.com/) and [axis-praxis.org](https://www.axis-praxis.org/); see also our [Variable fonts guide](css_fonts/variable_fonts_guide) for more information and usage information.

## Reference

### Properties

- [`font`](font)
- [`font-family`](font-family)
- [`font-feature-settings`](font-feature-settings)
- [`font-kerning`](font-kerning)
- [`font-language-override`](font-language-override)
- [`font-optical-sizing`](font-optical-sizing)
- [`font-size`](font-size)
- [`font-size-adjust`](font-size-adjust)
- [`font-stretch`](font-stretch)
- [`font-style`](font-style)
- [`font-synthesis`](font-synthesis)
- [`font-variant`](font-variant)
- [`font-variant-alternates`](font-variant-alternates)
- [`font-variant-caps`](font-variant-caps)
- [`font-variant-east-asian`](font-variant-east-asian)
- [`font-variant-ligatures`](font-variant-ligatures)
- [`font-variant-numeric`](font-variant-numeric)
- [`font-variant-position`](font-variant-position)
- [`font-variation-settings`](font-variation-settings)
- [`font-weight`](font-weight)
- [`line-height`](line-height)

### At-rules

[`@font-face`](@font-face)

- [`font-family`](@font-face/font-family)
- <span class="page-not-created">`font-feature-settings`</span>
- [`font-style`](@font-face/font-style)
- [`font-variant`](@font-face/font-variant)
- [`font-weight`](@font-face/font-weight)
- [`font-stretch`](@font-face/font-stretch)
- [`src`](@font-face/src)
- [`unicode-range`](@font-face/unicode-range)

[`@font-feature-values`](@font-feature-values)

## Guides

[Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)  
In this beginner's learning article we go through all the basic fundamentals of text/font styling in detail, including setting font weight, family and style, font shorthand, text alignment and other effects, and line and letter spacing.

[OpenType font features guide](css_fonts/opentype_fonts_guide)  
Font features or variants refer to different glyphs or character styles contained within an OpenType font. These include things like ligatures (special glyphs that combine characters like 'fi' or 'ffl'), kerning (adjustments to the spacing between specific letterform pairings), fractions, numeral styles, and a number of others. These are all referred to as OpenType Features, and are made available to use on the web via specific properties and a low-level control property — [`font-feature-settings`](font-feature-settings). This article provides you with all you need to know about using OpenType font features in CSS.

[Variable fonts guide](css_fonts/variable_fonts_guide)  
**Variable fonts** are an evolution of the OpenType font specification that enables many different variations of a typeface to be incorporated into a single file, rather than having a separate font file for every width, weight, or style. This article will give you all you need to know to get you started using variable fonts.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/">CSS Fonts Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>font-variation-settings</code> (and related higher-level properties) and <code>font-optical-sizing</code>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-3/">CSS Fonts Module Level 3</a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds <code>font-feature-settings</code> (and related higher-level properties)</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/fonts.html#font-shorthand">CSS Level 2 (Revision 1)</a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#font">CSS Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts</a>

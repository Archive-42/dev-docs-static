# font-variation-settings

The `font-variation-settings` CSS property provides low-level control over [variable font](css_fonts/variable_fonts_guide) characteristics, by specifying the four letter axis names of the characteristics you want to vary, along with their values.

## Syntax

    /* Use the default settings */
    font-variation-settings: normal;

    /* Set values for variable font axis names */
    font-variation-settings: "XHGT" 0.7;

    /* Global values */
    font-variation-settings: inherit;
    font-variation-settings: initial;
    font-variation-settings: unset;

### Values

This property's value can take one of two forms:

`normal`  
Text is laid out using default settings.

`<string> <number>`  
When rendering text, the list of variable font axis names is passed to the text layout engine to enable or disable font features. Each setting is always one or more pairs consisting of a [`<string>`](string) of 4 ASCII characters followed by a [`<number>`](number) indicating the axis value to set. If the `<string>` has more or fewer characters or contains characters outside the U+20 - U+7E codepoint range, the whole property is invalid. The `<number>` can be fractional or negative, depending on the value range available in your font, as defined by the font designer.

## Description

This property is a low-level mechanism designed to set variable font features where no other way to enable or access those features exist. You should only use it when no basic properties exist to set those features (e.g. [`font-weight`](font-weight), [`font-style`](font-style)).

Font characteristics set using `font-variation-settings` will always override those set using the corresponding basic font properties, e.g. `font-weight`, no matter where they appear in the cascade. In some browsers, this is currently only true when the `@font-face` declaration includes a `font-weight` range.

### Registered and custom axes

Variable font axes come in two types: **registered** and **custom**.

Registered axes are the most commonly encountered — common enough that the authors of the specification felt they were worth standardizing. Note that this doesn't mean that the author has to include all of these in their font.

Here are the registered axes along with their corresponding CSS properties:

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Axis Tag</th><th>CSS Property</th></tr></thead><tbody><tr class="odd"><td>"wght"</td><td><a href="font-weight"><code>font-weight</code></a></td></tr><tr class="even"><td>"wdth"</td><td><a href="font-stretch"><code>font-stretch</code></a></td></tr><tr class="odd"><td>"slnt" (slant)</td><td><a href="font-style"><code>font-style</code></a>: <code>oblique + angle</code></td></tr><tr class="even"><td>"ital"</td><td><a href="font-style"><code>font-style</code></a>: <code>italic</code></td></tr><tr class="odd"><td>"opsz"</td><td><p><a href="font-optical-sizing"><code>font-optical-sizing</code></a></p></td></tr></tbody></table>

Custom axes can be anything the font designer wants to vary in their font, for example ascender or descender heights, the size of serifs, or anything else they can imagine. Any axis can be used as long as it is given a unique 4-character axis. Some will end up becoming more common, and may even become registered over time.

**Note**: Registered axis tags are identified using lower-case tags, whereas custom axes should be given upper-case tags. Note that font designers aren't forced follow this practice in any way, and some won't. The important takeaway here is that axis tags are case-sensitive.

In order to use variable fonts on your operating system, you need to make sure that it is up to date. For example Linux OSes need the latest Linux Freetype version, and macOS prior to 10.13 does not support variable fonts. If your operating system is not up to date, you will not be able to use variable fonts in web pages or the Firefox Developer Tools.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a transform</td></tr></tbody></table>

## Formal syntax

    normal | [ <string> <number> ]#

## Examples

You can find a number of other variable fonts examples at our [Variable fonts guide](css_fonts/variable_fonts_guide), [v-fonts.com](https://v-fonts.com/), and [axis-praxis.org](https://www.axis-praxis.org/).

### Weight (wght)

The following live example's CSS can be edited to allow you to play with font weight values.

### Slant (slnt)

The following live example's CSS can be edited to allow you to play with font slant/oblique values.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#descdef-font-face-font-variation-settings">CSS Fonts Module Level 4<br />
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

17

62

No

49

11

Requires macOS 10.13 High Sierra or later.

62

62

62

46

11

Requires iOS 11 or later.

8.0

## See also

- [Variable fonts guide](css_fonts/variable_fonts_guide)
- [OpenType Font Variations Overview](https://www.microsoft.com/typography/otspec180/otvaroverview.htm)
- [OpenType Design-Variation Axis Tag Registry](https://www.microsoft.com/typography/otspec/dvaraxisreg.htm)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-variation-settings" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-variation-settings</a>

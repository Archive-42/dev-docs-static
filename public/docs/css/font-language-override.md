# font-language-override

The `font-language-override` CSS property controls the use of language-specific glyphs in a typeface.

    /* Keyword value */
    font-language-override: normal;

    /* <string> values */
    font-language-override: "ENG";  /* Use English glyphs */
    font-language-override: "TRK";  /* Use Turkish glyphs */

    /* Global values */
    font-language-override: initial;
    font-language-override: inherit;
    font-language-override: unset;

By default, HTML's `lang` attribute tells browsers to display glyphs designed specifically for that language. For example, a lot of fonts have a special character for the digraph `fi` that merge the dot on the "i" with the "f." However, if the language is set to Turkish the typeface will likely know not to use the merged glyph; Turkish has two versions of the "i," one with a dot (`i`) and one without (`ı`), and using the ligature would incorrectly transform a dotted "i" into a dotless "i."

The `font-language-override` property lets you override the typeface behavior for a specific language. This is useful, for example, when the typeface you're using lacks proper support for the language. For instance, if a typeface doesn't have proper rules for the Azeri language, you can force the font to use Turkish glyphs, which follow similar rules.

## Syntax

The `font-language-override` property is specified as the keyword `normal` or a `<string>`.

### Values

`normal`  
Tells the browser to use font glyphs that are appropriate for the language specified by the `lang` attribute. This is the default value.

[`<string>`](string)  
Tells the browser to use font glyphs that are appropriate for the language specified by the string. The string must match a language tag found in the [OpenType language system](https://www.microsoft.com/typography/otspec/languagetags.htm). For example, "ENG" is English, and "KOR" is Korean.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | <string>

## Examples

### Using Danish glyphs

#### HTML

    <p class="para1">Default language setting.</p>
    <p class="para2">This is a string with the <code>font-language-override</code> set to Danish.</p>

#### CSS

    p.para1 {
      font-language-override: normal;
    }

    p.para2 {
      font-language-override: "DAN";
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#propdef-font-language-override">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-language-override' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`font-language-override`

No

No

34

4

No

No

No

No

No

34

4

No

No

No

## See also

- [`font-variant`](font-variant), [`font-variant-position`](font-variant-position), [`font-variant-east-asian`](font-variant-east-asian), [`font-variant-caps`](font-variant-caps), [`font-variant-ligatures`](font-variant-ligatures), [`font-variant-numeric`](font-variant-numeric), [`font-variant-alternates`](font-variant-alternates), [`font-synthesis`](font-synthesis), [`font-kerning`](font-kerning).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-language-override" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-language-override</a>

# font-family

The `font-family` CSS property specifies a prioritized list of one or more font family names and/or generic family names for the selected element.

Values are separated by commas to indicate that they are alternatives. The browser will select the first font in the list that is installed or that can be downloaded using a [`@font-face`](@font-face) at-rule.

It is often convenient to use the shorthand property [`font`](font) to set `font-size` and other font related properties all at once.

You should always include at least one generic family name in a `font-family` list, since there's no guarantee that any given font is available. This lets the browser select an acceptable fallback font when necessary.

The `font-family` property specifies a list of fonts, from highest priority to lowest. Font selection _does not_ stop at the first font in the list that is on the user's system. Rather, font selection is done _one character at a time_, so that if an available font does not have a glyph for a needed character, the latter fonts are tried. (However, this doesn't work in Internet Explorer 6 or earlier.) When a font is only available in some [styles](font-style), [variants](font-variant), or [sizes](font-size), those properties may also influence which font family is chosen.

## Syntax

    /* A font family name and a generic family name */
    font-family: Gill Sans Extrabold, sans-serif;
    font-family: "Goudy Bookletter 1911", sans-serif;

    /* A generic family name only */
    font-family: serif;
    font-family: sans-serif;
    font-family: monospace;
    font-family: cursive;
    font-family: fantasy;
    font-family: system-ui;
    font-family: ui-serif;
    font-family: ui-sans-serif;
    font-family: ui-monospace;
    font-family: ui-rounded;
    font-family: emoji;
    font-family: math;
    font-family: fangsong;

    /* Global values */
    font-family: inherit;
    font-family: initial;
    font-family: unset;

The `font-family` property lists one or more font families, separated by commas. Each font family is specified as either a `<family-name>` or a `<generic-name>` value.

The example below lists two font families, the first with a `<family-name>` and the second with a `<generic-name>`:

    font-family: Gill Sans Extrabold, sans-serif;

### Values

`<family-name>`  
The name of a font family. For example, "Times" and "Helvetica" are font families. Font family names containing whitespace should be quoted.

`<generic-name>`  
Generic font families are a fallback mechanism, a means of preserving some of the style sheet author's intent when none of the specified fonts are available. Generic family names are keywords and must not be quoted. A generic font family should be the last item in the list of font family names. The following keywords are defined:

`serif`  
Glyphs have finishing strokes, flared or tapering ends, or have actual serifed endings.  
E.g. Lucida Bright, Lucida Fax, Palatino, "Palatino Linotype", Palladio, "URW Palladio", serif.

`sans-serif`  
Glyphs have stroke endings that are plain.  
E.g. "Open Sans", "Fira Sans", "Lucida Sans", "Lucida Sans Unicode", "Trebuchet MS", "Liberation Sans", "Nimbus Sans L", sans-serif.

`monospace`  
All glyphs have the same fixed width.  
E.g. "Fira Mono", "DejaVu Sans Mono", Menlo, Consolas, "Liberation Mono", Monaco, "Lucida Console", monospace.

`cursive`  
Glyphs in cursive fonts generally have either joining strokes or other cursive characteristics beyond those of italic typefaces. The glyphs are partially or completely connected, and the result looks more like handwritten pen or brush writing than printed letterwork.  
E.g. "Brush Script MT", "Brush Script Std", "Lucida Calligraphy", "Lucida Handwriting", "Apple Chancery", cursive.

`fantasy`  
Fantasy fonts are primarily decorative fonts that contain playful representations of characters.  
E.g. Papyrus, Herculanum, Party LET, Curlz MT, Harrington, fantasy.

`system-ui`  
Glyphs are taken from the default user interface font on a given platform. Because typographic traditions vary widely across the world, this generic is provided for typefaces that don't map cleanly into the other generics. This is example system-ui text.

`ui-serif`  
The default user interface serif font. This is example ui-serif text.

`ui-sans-serif`  
The default user interface sans-serif font. This is example ui-sans-serif text.

`ui-monospace`  
The default user interface monospace font. This is example ui-monospace text.

`ui-rounded`  
The default user interface font that has rounded features. This is example ui-rounded text.

`math`  
This is for the particular stylistic concerns of representing mathematics: superscript and subscript, brackets that cross several lines, nesting expressions, and double struck glyphs with distinct meanings. This is some example math text: ax² + bx + c = 0.

`emoji`  
Fonts that are specifically designed to render emoji. This is some example emoji text: ✝♾.

`fangsong`  
A particular style of Chinese characters that are between serif-style Song and cursive-style Kai forms. This style is often used for government documents. This is some example fangsong text with the Chinese characters for "fangsong" in traditional and simple forms, respectively: 仿宋體 仿宋体.

### Valid family names

Font family names must either be given quoted as strings, or unquoted as a sequence of one or more identifiers. This means that punctuation characters and digits at the start of each token must be escaped in unquoted font family names.

For example, the following declarations are valid:

    font-family: Gill Sans Extrabold, sans-serif;
    font-family: "Goudy Bookletter 1911", sans-serif;

The following declarations are **invalid**:

    font-family: Goudy Bookletter 1911, sans-serif;
    font-family: Red/Black, sans-serif;
    font-family: "Lucida" Grande, sans-serif;
    font-family: Ahem!, sans-serif;
    font-family: test@foo, sans-serif;
    font-family: #POUND, sans-serif;
    font-family: Hawaii 5-0, sans-serif;

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>depends on user agent</td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ <family-name> | <generic-family> ]#where
    <family-name> = <string> | <custom-ident>+
    <generic-family> = serif | sans-serif | cursive | fantasy | monospace

## Examples

### Some common font families

    .serif {
      font-family: Times, Times New Roman, Georgia, serif;
    }

    .sansserif {
      font-family: Verdana, Arial, Helvetica, sans-serif;
    }

    .monospace {
      font-family: Lucida Console, Courier, monospace;
    }

    .cursive {
      font-family: cursive;
    }

    .fantasy {
      font-family: fantasy;
    }

    .emoji {
      font-family: emoji;
    }

    .math {
      font-family: math;
    }

    .fangsong {
      font-family: fangsong;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#generic-font-families">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'generic font families' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds new generic font families, specifically: <code>system-ui</code>, <code>ui-serif</code>, <code>ui-sans-serif</code>, <code>ui-monospace</code>, <code>ui-rounded</code>, <code>emoji</code>, <code>math</code>, and <code>fangsong</code>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-3/#font-family-prop">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-family' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/fonts.html#propdef-font-family">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'font-family' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#font-family">CSS Level 1<br />
<span class="small">The definition of 'font-family' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-family`

1

12

1

Not supported on `option` elements. See [bug 1536148](https://bugzil.la/1536148).

3

3.5

1

1

18

4

10.1

1

1.0

`system_ui`

56

79

No

43

Supported on macOS only.

No

43

9

Supported since macOS 10.11.

56

56

No

43

9

6.0

## See also

- [`font-style`](font-style)
- [`font-weight`](font-weight)
- [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-family" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-family</a>

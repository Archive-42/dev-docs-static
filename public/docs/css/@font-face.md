# @font-face

The `@font-face` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [at-rule](at-rule) specifies a custom font with which to display text; the font can be loaded from either a remote server or a locally-installed font on the user's own computer.

## Syntax

    @font-face {
      font-family: "Open Sans";
      src: url("/fonts/OpenSans-Regular-webfont.woff2") format("woff2"),
           url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
    }

### Descriptors

[`ascent-override`](@font-face/ascent-override)  
Defines the ascent metric for the font.

[`descent-override`](@font-face/descent-override)  
Defines the descent metric for the font.

[`font-display`](@font-face/font-display)  
Determines how a font face is displayed based on whether and when it is downloaded and ready to use.

[`font-family`](@font-face/font-family)  
Specifies a name that will be used as the font face value for font properties.

[`font-stretch`](@font-face/font-stretch)  
A [`font-stretch`](font-stretch) value. Accepts two values to specify a range that is supported by a font-face, for example `font-stretch: 50% 200%;`

[`font-style`](@font-face/font-style)  
A [`font-style`](font-style) value. Accepts two values to specify a range that is supported by a font-face, for example `font-style: oblique 20deg 50deg;`

[`font-weight`](@font-face/font-weight)  
A [`font-weight`](font-weight) value. Accepts two values to specify a range that is supported by a font-face, for example `font-weight: 100 400;`

[`font-variant`](@font-face/font-variant)  
A [`font-variant`](font-variant) value.

[`font-feature-settings`](font-feature-settings)  
Allows control over advanced typographic features in OpenType fonts.

[`font-variation-settings`](@font-face/font-variation-settings)  
Allows low-level control over OpenType or TrueType font variations, by specifying the four letter axis names of the features to vary, along with their variation values.

[`line-gap-override`](@font-face/line-gap-override)  
Defines the line gap metric for the font.

[`src`](@font-face/src)  
Specifies the resource containing the font data. This can be a URL to a remote font file location or the name of a font on the user's computer.

To provide the browser with a hint as to what format a font resource is — so it can select a suitable one — it is possible to include a format type inside a `format()` function:

    src: url(ideal-sans-serif.woff) format("woff"),
         url(basic-sans-serif.ttf) format("truetype");

The available types are: `"woff"`, `"woff2"`, `"truetype"`, `"opentype"`, `"embedded-opentype"`, and `"svg"`.

[`size-adjust`](@font-face/size-adjust)<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Defines a multiplier for glyph outlines and metrics associated with this font. This makes it easier to harmonize the designs of various fonts when rendered at the same font size.

[`unicode-range`](@font-face/unicode-range)  
The range of Unicode code points to be used from the font.

## Description

If the `local()` function is provided, specifying a font name to look for on the user's computer, and the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) finds a match, that local font is used. Otherwise, the font resource specified using the `url()` function is downloaded and used.

By allowing authors to provide their own fonts, `@font-face` makes it possible to design content without being limited to the so-called "web-safe" fonts (that is, the fonts which are so common that they're considered to be universally available). The ability to specify the name of a locally-installed font to look for and use makes it possible to customize the font beyond the basics while making it possible to do so without relying on an Internet connection.

It's common to use both `url()` and `local()` together, so that the user's installed copy of the font is used if available, falling back to downloading a copy of the font if it's not found on the user's device.

The `@font-face` at-rule may be used not only at the top level of a CSS, but also inside any [CSS conditional-group at-rule](at-rule#conditional_group_rules).

### Font MIME Types

<table><thead><tr class="header"><th>Format</th><th>MIME type</th></tr></thead><tbody><tr class="odd"><td>TrueType</td><td><code>font/ttf</code></td></tr><tr class="even"><td>OpenType</td><td><code>font/otf</code></td></tr><tr class="odd"><td>Web Open Font Format</td><td><code>font/woff</code></td></tr><tr class="even"><td>Web Open Font Format 2</td><td><code>font/woff2</code></td></tr></tbody></table>

### Notes

- Web fonts are subject to the same domain restriction (font files must be on the same domain as the page using them), unless [HTTP access controls](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) are used to relax this restriction.
- `@font-face` cannot be declared within a CSS selector. For example, the following will not work:

      .className {
        @font-face {
          font-family: MyHelvetica;
          src: local("Helvetica Neue Bold"),
               local("HelveticaNeue-Bold"),
               url(MgOpenModernaBold.ttf);
          font-weight: bold;
        }
      }

## Formal syntax

    @font-face {
      [ font-family: <family-name>; ] ||
      [ src: <src>; ] ||
      [ unicode-range: <unicode-range>; ] ||
      [ font-variant: <font-variant>; ] ||
      [ font-feature-settings: <font-feature-settings>; ] ||
      [ font-variation-settings: <font-variation-settings>; ] ||
      [ font-stretch: <font-stretch>; ] ||
      [ font-weight: <font-weight>; ] ||
      [ font-style: <font-style>; ]
    }where
    <family-name> = <string> | <custom-ident>+

## Examples

### Specifying a downloadable font

This example specifies a downloadable font to use, applying it to the entire body of the document:

    <html>
    <head>
      <title>Web Font Sample</title>
      <style type="text/css" media="screen, print">
        @font-face {
          font-family: "Bitstream Vera Serif Bold";
          src: url("https://mdn.mozillademos.org/files/2468/VeraSeBd.ttf");
        }

        body { font-family: "Bitstream Vera Serif Bold", serif }
      </style>
    </head>
    <body>
      This is Bitstream Vera Serif Bold.
    </body>
    </html>

The output of this example code looks like so:

### Specifying local font alternatives

In this example, the user's local copy of "Helvetica Neue Bold" is used; if the user does not have that font installed (two different names are tried), then the downloadable font named "MgOpenModernaBold.ttf" is used instead:

    @font-face {
      font-family: MyHelvetica;
      src: local("Helvetica Neue Bold"),
           local("HelveticaNeue-Bold"),
           url(MgOpenModernaBold.ttf);
      font-weight: bold;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-5/#font-face-rule">CSS Fonts Module Level 5<br />
<span class="small">The definition of '@font-face' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>size-adjust</code> descriptor.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-face-rule">CSS Fonts Module Level 4<br />
<span class="small">The definition of '@font-face' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Definition in this version of the specification.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/WOFF2/">WOFF File Format 2.0<br />
<span class="small">The definition of 'WOFF2 font format' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Font format specification with new compression algorithm</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/WOFF/">WOFF File Format 1.0<br />
<span class="small">The definition of 'WOFF font format' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Font format specification</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#font-face-rule">CSS Fonts Module Level 3<br />
<span class="small">The definition of '@font-face' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`@font-face`

1

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

`SVG_fonts`

1-38

No

No

No

15-25

3.2

≤37-38

18-38

No

14-25

3

1.0-3.0

`WOFF`

6

12

3.5

9

11.1

5.1

4.4

18

4

11.1

5

1.0

`WOFF_2`

36

14

39

No

23

10

Supported only on macOS 10.12 (Sierra) and later.

37

36

39

24

10

3.0

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

`font-family`

4

12

3.5

6

10

3.1

2.2

18

4

10.1

3.1

1.0

`font-feature-settings`

No

No

34

The [ISO/IEC CD 14496-22 3rd edition](http://mpeg.chiariglione.org/standards/mpeg-4/open-font-format/text-isoiec-cd-14496-22-3rd-edition) suggests using the `ssty` feature to provide glyph variants more suitable for use in scripts (for example primes used as superscripts). Starting with Firefox 29, this is done automatically by the [MathML](https://developer.mozilla.org/docs/Web/MathML) rendering engine. The ISO/IEC CD 14496-22 3rd edition also suggests applying the `dtls` feature to letters when placing mathematical accents to get dotless forms (for example dotless i, j with a hat). Starting with Firefox 35, this is done automatically by the MathML rendering engine. You can override the default values determined by the MathML rendering engine with CSS.

15

From Firefox 4 to Firefox 14 (inclusive), Firefox supported an older, slightly different syntax. See [OpenType Font Feature support in Firefox 4](http://hacks.mozilla.org/2010/11/firefox-4-font-feature-support/).

No

No

No

No

No

34

The [ISO/IEC CD 14496-22 3rd edition](http://mpeg.chiariglione.org/standards/mpeg-4/open-font-format/text-isoiec-cd-14496-22-3rd-edition) suggests using the `ssty` feature to provide glyph variants more suitable for use in scripts (for example primes used as superscripts). Starting with Firefox 29, this is done automatically by the [MathML](https://developer.mozilla.org/docs/Web/MathML) rendering engine. The ISO/IEC CD 14496-22 3rd edition also suggests applying the `dtls` feature to letters when placing mathematical accents to get dotless forms (for example dotless i, j with a hat). Starting with Firefox 35, this is done automatically by the MathML rendering engine. You can override the default values determined by the MathML rendering engine with CSS.

15

From Firefox 4 to Firefox 14 (inclusive), Firefox supported an older, slightly different syntax. See [OpenType Font Feature support in Firefox 4](http://hacks.mozilla.org/2010/11/firefox-4-font-feature-support/).

No

No

No

`font-stretch`

62

17

62

No

49

10.1

62

62

62

41

10.3

6.0

`font-style`

4

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

`font-variant`

4

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

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

`font-weight`

4

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

`size-adjust`

No

No

89

No

No

No

No

No

No

No

No

No

`src`

4

12

3.5

6

10

3.1

2.2

18

4

10.1

3.1

1.0

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

- [About WOFF](https://developer.mozilla.org/en-US/docs/Web/Guide/WOFF)
- [Everythingfonts font-face generator](https://everythingfonts.com/font-face)
- [FontSquirrel @font-face generator](https://www.fontsquirrel.com/fontface/generator)
- [Beautiful fonts with @font-face](https://hacks.mozilla.org/2009/06/beautiful-fonts-with-font-face/)
- [Open Font Library](https://openfontlibrary.org/)
- [When can I use WOFF?](https://caniuse.com/woff)
- [When can I use SVG Fonts?](https://caniuse.com/svg-fonts)
- [Free Fancy Cool Fonts](https://coolfont.org)
- [Best Nicknames](https://nicknames.name/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face</a>

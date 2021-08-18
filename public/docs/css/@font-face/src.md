# src

The `src` CSS descriptor of the [`@font-face`](../@font-face) rule specifies the resource containing font data. It is required for the `@font-face` rule to be valid.

## Syntax

    /* <url> values */
    src: url(https://somewebsite.com/path/to/font.woff); /* Absolute URL */
    src: url(path/to/font.woff);                         /* Relative URL */
    src: url(path/to/font.woff) format("woff");          /* Explicit format */
    src: url('path/to/font.woff');                       /* Quoted URL */
    src: url(path/to/svgfont.svg#example);               /* Fragment identifying font */

    /* <font-face-name> values */
    src: local(font);      /* Unquoted name */
    src: local(some font); /* Name containing space */
    src: local("font");    /* Quoted name */

    /* Multiple items */
    src: local(font), url(path/to/font.svg) format("svg"),
         url(path/to/font.woff) format("woff"),
         url(path/to/font.otf) format("opentype");

### Values

`<url> [ format( <string># ) ]?`  
Specifies an external reference consisting of a [`<url>()`](<../url()>), followed by an optional hint using the `format()` function to describe the format of the font resource referenced by that URL. The format hint contains a comma-separated list of format strings that denote well-known font formats. If a user agent doesn't support the specified formats, it skips downloading the font resource. If no format hints are supplied, the font resource is always downloaded.

`<font-face-name>`  
Specifies the name of a locally-installed font face using the `local()` function, which uniquely identifies a single font face within a larger family. The name can optionally be enclosed in quotes.

## Description

The value of this descriptor is a prioritized, comma-separated list of external references or locally-installed font face names. When a font is needed the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) iterates over the set of references listed using the first one it can successfully activate. Fonts containing invalid data or local font faces that are not found are ignored and the user agent loads the next font in the list.

As with other URLs in CSS, the URL may be relative, in which case it is resolved relative to the location of the style sheet containing the `@font-face` rule. In the case of SVG fonts, the URL points to an element within a document containing SVG font definitions. If the element reference is omitted, a reference to the first defined font is implied. Similarly, font container formats that can contain more than one font load only one of the fonts for a given `@font-face` rule. Fragment identifiers are used to indicate which font to load. If a container format lacks a defined fragment identifier scheme, a simple 1-based indexing scheme (e.g., "font-collection\#1" for the first font, "font-collection\#2" for the second font, etc.) is used.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@font-face"><code>@font-face</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>n/a (required)</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    [ <url> [ format( <string># ) ]? | local( <family-name> ) ]#where
    <family-name> = <string> | <custom-ident>+

## Examples

### Specifying font resources using url() and local()

    @font-face {
      font-family: examplefont;
      src: local(Example Font),
           url('examplefont.woff') format("woff"),
           url('examplefont.otf') format("opentype");
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#src-desc">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'src' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`format_keyword`

No

No

No

No

No

4

No

No

No

No

5

No

## See also

- [`font-display`](font-display)
- [`font-family`](font-family)
- [`font-stretch`](font-stretch)
- [`font-style`](font-style)
- [`font-weight`](font-weight)
- [`font-variant`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`font-variation-settings`](font-variation-settings)
- [`unicode-range`](unicode-range)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/src" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/src</a>

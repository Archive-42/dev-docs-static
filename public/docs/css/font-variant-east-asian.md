# font-variant-east-asian

The `font-variant-east-asian` CSS property controls the use of alternate glyphs for East Asian scripts, like Japanese and Chinese.

    font-variant-east-asian: normal;
    font-variant-east-asian: ruby;
    font-variant-east-asian: jis78;              /* <east-asian-variant-values> */
    font-variant-east-asian: jis83;              /* <east-asian-variant-values> */
    font-variant-east-asian: jis90;              /* <east-asian-variant-values> */
    font-variant-east-asian: jis04;              /* <east-asian-variant-values> */
    font-variant-east-asian: simplified;         /* <east-asian-variant-values> */
    font-variant-east-asian: traditional;        /* <east-asian-variant-values> */
    font-variant-east-asian: full-width;         /* <east-asian-width-values> */
    font-variant-east-asian: proportional-width; /* <east-asian-width-values> */
    font-variant-east-asian: ruby full-width jis83;

    /* Global values */
    font-variant-east-asian: inherit;
    font-variant-east-asian: initial;
    font-variant-east-asian: unset;

## Syntax

### Values

`normal`  
This keyword leads to the deactivation of the use of such alternate glyphs.

`ruby`  
This keyword forces the use of special glyphs for ruby characters. As these are usually smaller, font creators often designs specific forms, usually slightly bolder to improve the contrast. This keyword corresponds to the OpenType values `ruby`.

`<east-asian-variant-values>`  
These values specify a set of logographic glyph variants which should be used for display. Possible values are:

<table><thead><tr class="header"><th>Keyword</th><th>Standard defining the glyphs</th><th>OpenType equivalent</th></tr></thead><tbody><tr class="odd"><td><code>jis78</code></td><td><a href="https://en.wikipedia.org/wiki/JIS_X_0208#First_standard">JIS X 0208:1978</a></td><td><code>jp78</code></td></tr><tr class="even"><td><code>jis83</code></td><td><a href="https://en.wikipedia.org/wiki/JIS_X_0208#Second_standard">JIS X 0208:1983</a></td><td><code>jp83</code></td></tr><tr class="odd"><td><code>jis90</code></td><td><a href="https://en.wikipedia.org/wiki/JIS_X_0208#Third_standard">JIS X 0208:1990</a></td><td><code>jp90</code></td></tr><tr class="even"><td><code>jis04</code></td><td><a href="https://en.wikipedia.org/wiki/JIS_X_0213">JIS X 0213:2004</a></td><td><code>jp04</code></td></tr><tr class="odd"><td><code>simplified</code></td><td>None, use the simplified Chinese glyphs</td><td><code>smpl</code></td></tr><tr class="even"><td><code>traditional</code></td><td>None, use the traditional Chinese glyphs</td><td><code>trad</code></td></tr></tbody></table>

`<east-asian-width-values>`  
These values control the sizing of figures used for East Asian characters. Two values are possible:

- `proportional-width` activating the set of East Asian characters which vary in width. It corresponds to the OpenType values `pwid`.
- `full-width` activating the set of East Asian characters which are all of the same, roughly square, width metric. It corresponds to the OpenType values `fwid`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | [ <east-asian-variant-values> || <east-asian-width-values> || ruby ]where
    <east-asian-variant-values> = [ jis78 | jis83 | jis90 | jis04 | simplified | traditional ]
    <east-asian-width-values> = [ full-width | proportional-width ]

## Examples

### Setting East Asian glyph variants

This example require font "Yu Gothic" installed in your OS, other fonts may not support OpenType features.

#### HTML

    <table>
    <thead></thead>
    <tbody style="border:0;">
      <tr>
        <th>normal/jis78:</th>
        <td>麹町</td>
        <td class="jis78">麹町</td>
      </tr>
      <tr>
        <th>normal/ruby:</th>
        <td>しんかんせん</td>
        <td class="ruby">しんかんせん</td>
      </tr>
      <tr>
        <th>normal/traditional:</th>
        <td>大学</td>
        <td class="traditional">大学</td>
      </tr>
    </tbody>
    </table>

#### CSS

    td{
      font-family:"Yu Gothic";
      font-size:20px;
    }
    th{
      color:grey;
      padding-right:10px;
    }

    .ruby {
      font-variant-east-asian: ruby;
    }

    .jis78 {
      font-variant-east-asian: jis78;
    }

    .traditional{
      font-variant-east-asian: traditional;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#propdef-font-variant-east-asian">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-variant-east-asian' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-variant-east-asian`

63

79

34

No

50

No

63

63

34

46

No

8.0

## See Also

- [`font-variant-alternates`](font-variant-alternates)
- [`font-variant-caps`](font-variant-caps)
- [`font-variant`](font-variant)
- [`font-variant-ligatures`](font-variant-ligatures)
- [`font-variant-numeric`](font-variant-numeric)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian</a>

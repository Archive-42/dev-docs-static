# text-rendering

The `text-rendering` CSS property provides information to the rendering engine about what to optimize for when rendering text.

The browser makes trade-offs among speed, legibility, and geometric precision.

    /* Keyword values */
    text-rendering: auto;
    text-rendering: optimizeSpeed;
    text-rendering: optimizeLegibility;
    text-rendering: geometricPrecision;

    /* Global values */
    text-rendering: inherit;
    text-rendering: initial;
    text-rendering: unset;

**Note:** The `text-rendering` property is an SVG property that is not defined in any CSS standard. However, Gecko and WebKit browsers let you apply this property to HTML and XML content on Windows, macOS, and Linux.

One very visible effect is `optimizeLegibility`, which enables ligatures (ff, fi, fl, etc.) in text smaller than 20px for some fonts (for example, Microsoft's _Calibri_, _Candara_, _Constantia_, and _Corbel_, or the _DejaVu_ font family).

## Syntax

### Values

`auto`  
The browser makes educated guesses about when to optimize for speed, legibility, and geometric precision while drawing text. For differences in how this value is interpreted by the browser, see the compatibility table.

`optimizeSpeed`  
The browser emphasizes rendering speed over legibility and geometric precision when drawing text. It disables kerning and ligatures.

`optimizeLegibility`  
The browser emphasizes legibility over rendering speed and geometric precision. This enables kerning and optional ligatures.

`geometricPrecision`  
The browser emphasizes geometric precision over rendering speed and legibility. Certain aspects of fonts — such as kerning — don't scale linearly. So this value can make text using those fonts look good.

In SVG, when text is scaled up or down, browsers calculate the final size of the text (which is determined by the specified font size and the applied scale) and request a font of that computed size from the platform's font system. But if you request a font size of, say, 9 with a scale of 140%, the resulting font size of 12.6 doesn't explicitly exist in the font system, so the browser rounds the font size to 12 instead. This results in stair-step scaling of text.

But the `geometricPrecision` property — when fully supported by the rendering engine — lets you scale your text fluidly. For large scale factors, you might see less-than-beautiful text rendering, but the size is what you would expect—neither rounded up nor down to the nearest font size supported by Windows or Linux.

**Note**: WebKit precisely applies the specified value, but Gecko treats the value the same as `optimizeLegibility`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>text elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | optimizeSpeed | optimizeLegibility | geometricPrecision

## Examples

### Automatic application of optimizeLegibility

This demonstrates how `optimizeLegibility` is used by browsers automatically when the `font-size` is smaller than `20px`.

#### HTML

    <p class="small">LYoWAT - ff fi fl ffl</p>
    <p class="big">LYoWAT - ff fi fl ffl</p>

#### CSS

    .small { font: 19.9px "Constantia", "Times New Roman", "Georgia", "Palatino", serif; }
    .big   { font: 20px "Constantia", "Times New Roman", "Georgia", "Palatino", serif; }

#### Result

### optimizeSpeed vs optimizeLegibility

This example shows the difference between the appearance of `optimizeSpeed` and `optimizeLegibility` (in your browser; other browsers may vary).

#### HTML

    <p class="speed">LYoWAT - ff fi fl ffl</p>
    <p class="legibility">LYoWAT - ff fi fl ffl</p>

#### CSS

    p { font: 1.5em "Constantia", "Times New Roman", "Georgia", "Palatino", serif }

    .speed       { text-rendering: optimizeSpeed; }
    .legibility  { text-rendering: optimizeLegibility; }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/painting.html#TextRenderingProperty">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'text-rendering' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/painting.html#TextRenderingProperty">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'text-rendering' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-rendering`

4

\["This property is only supported on Windows and Linux.", "Initial versions had bugs on Windows and Linux that broke [font substitition](https://crbug.com/114719), [small-caps](https://crbug.com/51973), [letter-spacing](https://crbug.com/55458) or caused [text to overlap](https://crbug.com/149548)."\]

79

\["This property is only supported on Windows and Linux.", "Initial versions had bugs on Windows and Linux that broke [font substitition](https://crbug.com/114719), [small-caps](https://crbug.com/51973), [letter-spacing](https://crbug.com/55458) or caused [text to overlap](https://crbug.com/149548)."\]

1

\["This property is only supported on Windows and Linux.", "The `optimizeSpeed` option has no effect on Firefox 4 because the standard code for text rendering is already fast and there is not a faster code path at this time. See [bug 595688](https://bugzil.la/595688) for details."\]

No

15

5

3

From version 3 to 4.3, there is a serious bug where `text-rendering: optimizeLegibility` causes custom web fonts to not render. This was fixed in version 4.4.

18

\["This property is only supported on Windows and Linux.", "Initial versions had bugs on Windows and Linux that broke [font substitition](https://crbug.com/114719), [small-caps](https://crbug.com/51973), [letter-spacing](https://crbug.com/55458) or caused [text to overlap](https://crbug.com/149548)."\]

46

14

4.2

1.0

This property is only supported on Windows and Linux. Samsung Internet is not on Windows or Linux.

`auto`

4

Chrome treats `auto` as `optimizeSpeed`.

79

Edge treats `auto` as `optimizeSpeed`.

1

If the font size is 20 pixels or higher, Firefox treats `auto` as `optimizeLegibility`. For smaller text, Firefox treats `auto` as `optimizeSpeed`. The 20-pixel threshold can be changed with the `browser.display.auto_quality_min_font_size` preference.

No

15

Opera treats `auto` as `optimizeSpeed`.

5

Safari treats `auto` as `optimizeSpeed`. See [WebKit bug 41363](https://webkit.org/b/41363).

≤37

WebView treats `auto` as `optimizeSpeed`.

18

Chrome treats `auto` as `optimizeSpeed`.

46

If the font size is 20 pixels or higher, Firefox treats `auto` as `optimizeLegibility`. For smaller text, Firefox treats `auto` as `optimizeSpeed`. The 20-pixel threshold can be changed with the `browser.display.auto_quality_min_font_size` preference.

14

Opera treats `auto` as `optimizeSpeed`.

4.2

Safari treats `auto` as `optimizeSpeed`. See [WebKit bug 41363](https://webkit.org/b/41363).

1.0

Samsung Internet treats `auto` as `optimizeSpeed`.

`geometricPrecision`

13

Supports true geometric precision without rounding up or down to the nearest supported font size in the operating system.

79

Supports true geometric precision without rounding up or down to the nearest supported font size in the operating system.

1

Firefox treats `geometricPrecision` the same as `optimizeLegibility`.

No

15

Supports true geometric precision without rounding up or down to the nearest supported font size in the operating system.

6

37

Supports true geometric precision without rounding up or down to the nearest supported font size in the operating system.

18

Supports true geometric precision without rounding up or down to the nearest supported font size in the operating system.

46

Firefox treats `geometricPrecision` the same as `optimizeLegibility`.

14

Supports true geometric precision without rounding up or down to the nearest supported font size in the operating system.

6

1.0

Supports true geometric precision without rounding up or down to the nearest supported font size in the operating system.

## See also

- [Drawing text in a `<canvas>`](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)
- [CSS Text Decoration](css_text_decoration) CSS module
- Related CSS properties
  - `text-decoration` (and its longhand properties, such as `text-decoration-line`, `text-decoration-style`, and `text-decoration-thickness`)
  - `text-emphasis` (and its longhand properties, including `text-emphasis-color`, `text-emphasis-position`, and `text-emphasis-style`)
  - `text-shadow`
  - `text-transform`
- The [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG) `text-rendering` attribute
- [SVG and CSS](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/SVG_and_CSS)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-rendering" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-rendering</a>

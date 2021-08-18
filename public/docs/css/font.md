# font

The `font` CSS [shorthand property](shorthand_properties) sets all the different properties of an element's font. Alternatively, it sets an element's font to a system font.

As with any shorthand property, any individual value that is not specified is set to its corresponding initial value (possibly overriding values previously set using non-shorthand properties). Though not directly settable by `font`, the longhands [`font-size-adjust`](font-size-adjust) and [`font-kerning`](font-kerning) are also reset to their initial values.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`font-family`](font-family)
- [`font-size`](font-size)
- [`font-stretch`](font-stretch)
- [`font-style`](font-style)
- [`font-variant`](font-variant)
- [`font-weight`](font-weight)
- [`line-height`](line-height)

## Syntax

The `font` property may be specified as either a single keyword, which will select a system font, or as a shorthand for various font-related properties.

If `font` is specified as a system keyword, it must be one of: `caption`, `icon`, `menu`, `message-box`, `small-caption`, `status-bar`.

If `font` is specified as a shorthand for several font-related properties, then:

- it must include values for:
  - [`<font-size>`](font-size)
  - [`<font-family>`](font-family)
- it may optionally include values for:
  - [`<font-style>`](font-style)
  - [`<font-variant>`](font-variant)
  - [`<font-weight>`](font-weight)
  - [`<font-stretch>`](font-stretch)
  - [`<line-height>`](line-height)
- `font-style`, `font-variant` and `font-weight` must precede `font-size`
- `font-variant` may only specify the values defined in CSS 2.1, that is `normal` and `small-caps`
- `font-stretch` may only be a single keyword value.
- `line-height` must immediately follow `font-size`, preceded by "/", like this: "`16px/3`"
- `font-family` must be the last value specified.

### Values

`<'font-style'>`  
See the [`font-style`](font-style) CSS property.

`<'font-variant'>`  
See the [`font-variant`](font-variant) CSS property.

`<'font-weight'>`  
See the [`font-weight`](font-weight) CSS property.

`<'font-stretch'>`  
See the [`font-stretch`](font-stretch) CSS property.

`<'font-size'>`  
See the [`font-size`](font-size) CSS property.

`<'line-height'>`  
See the [`line-height`](line-height) CSS property.

`<'font-family'>`  
See the [`font-family`](font-family) CSS property.

#### System font values

`caption`  
The system font used for captioned controls (e.g., buttons, drop-downs, etc.).

`icon`  
The system font used to label icons.

`menu`  
The system font used in menus (e.g., dropdown menus and menu lists).

`message-box`  
The system font used in dialog boxes.

`small-caption`  
The system font used for labeling small controls.

`status-bar`  
The system font used in window status bars.

Prefixed system font keywords  
Browsers often implement several more, prefixed, keywords: Gecko implements `-moz-window`, `-moz-document`, `-moz-desktop`, `-moz-info`, `-moz-dialog`, `-moz-button`, `-moz-pull-down-menu`, `-moz-list`, and `-moz-field`.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="font-style"><code>font-style</code></a>: <code>normal</code></li><li><a href="font-variant"><code>font-variant</code></a>: <code>normal</code></li><li><a href="font-weight"><code>font-weight</code></a>: <code>normal</code></li><li><a href="font-stretch"><code>font-stretch</code></a>: <code>normal</code></li><li><a href="font-size"><code>font-size</code></a>: <code>medium</code></li><li><a href="line-height"><code>line-height</code></a>: <code>normal</code></li><li><a href="font-family"><code>font-family</code></a>: depends on user agent</li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td>Percentages</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="font-size"><code>font-size</code></a>: refer to the parent element's font size</li><li><a href="line-height"><code>line-height</code></a>: refer to the font size of the element itself</li></ul></td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="font-style"><code>font-style</code></a>: as specified</li><li><a href="font-variant"><code>font-variant</code></a>: as specified</li><li><a href="font-weight"><code>font-weight</code></a>: the keyword or the numerical value as specified, with <code>bolder</code> and <code>lighter</code> transformed to the real value</li><li><a href="font-stretch"><code>font-stretch</code></a>: as specified</li><li><a href="font-size"><code>font-size</code></a>: as specified, but with relative lengths converted into absolute lengths</li><li><a href="line-height"><code>line-height</code></a>: for percentage and length values, the absolute length, otherwise as specified</li><li><a href="font-family"><code>font-family</code></a>: as specified</li></ul></td></tr><tr class="even"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="font-style"><code>font-style</code></a>: discrete</li><li><a href="font-variant"><code>font-variant</code></a>: discrete</li><li><a href="font-weight"><code>font-weight</code></a>: a <a href="font-weight#interpolation">font weight</a></li><li><a href="font-stretch"><code>font-stretch</code></a>: a <a href="font-stretch#interpolation">font stretch</a></li><li><a href="font-size"><code>font-size</code></a>: a <a href="length#interpolation">length</a></li><li><a href="line-height"><code>line-height</code></a>: either number or length</li><li><a href="font-family"><code>font-family</code></a>: discrete</li></ul></td></tr></tbody></table>

## Formal syntax

    [ [ <'font-style'> || <font-variant-css21> || <'font-weight'> || <'font-stretch'> ]? <'font-size'> [ / <'line-height'> ]? <'font-family'> ] | caption | icon | menu | message-box | small-caption | status-barwhere
    <font-variant-css21> = [ normal | small-caps ]

## Examples

### Setting font properties

    /* Set the font size to 12px and the line height to 14px.
       Set the font family to sans-serif */
    p { font: 12px/14px sans-serif }

    /* Set the font size to 80% of the parent element
       or default value (if no parent element present).
       Set the font family to sans-serif */
    p { font: 80% sans-serif }

    /* Set the font weight to bold,
       the font-style to italic,
       the font size to large,
       and the font family to serif. */
    p { font: bold italic large serif }

    /* Use the same font as the status bar of the window */
    p { font: status-bar }

### Live sample

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#font-prop">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added support for <code>font-stretch</code> values.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/fonts.html#font-shorthand">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'font-weight' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added support for keywords.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#font">CSS Level 1<br />
<span class="small">The definition of 'font' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`font`

1

12

1

3

3.5

1

≤37

18

4

14

1

1.0

`font_stretch_support`

60

79

43

No

47

11

60

60

43

44

11

8.0

`system_fonts`

1

12

1

4

6

1

37

18

4

14

1

1.0

## See also

- [`font-style`](font-style)
- [`font-weight`](font-weight)
- [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font</a>

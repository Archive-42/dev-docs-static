# vertical-align

The `vertical-align` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets vertical alignment of an inline, inline-block or table-cell box.

The vertical-align property can be used in two contexts:

- To vertically align an inline element's box inside its containing line box. For example, it could be used to vertically position an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) in a line of text:

<!-- -->

- To vertically align the content of a cell in a table:

Note that `vertical-align` only applies to inline, inline-block and table-cell elements: you can't use it to vertically align [block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements).

## Syntax

    /* Keyword values */
    vertical-align: baseline;
    vertical-align: sub;
    vertical-align: super;
    vertical-align: text-top;
    vertical-align: text-bottom;
    vertical-align: middle;
    vertical-align: top;
    vertical-align: bottom;

    /* <length> values */
    vertical-align: 10em;
    vertical-align: 4px;

    /* <percentage> values */
    vertical-align: 20%;

    /* Global values */
    vertical-align: inherit;
    vertical-align: initial;
    vertical-align: unset;

The `vertical-align` property is specified as one of the values listed below.

### Values for inline elements

#### Parent-relative values

These values vertically align the element relative to its parent element:

`baseline`  
Aligns the baseline of the element with the baseline of its parent. The baseline of some [replaced elements](replaced_element), like [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea), is not specified by the HTML specification, meaning that their behavior with this keyword may vary between browsers.

`sub`  
Aligns the baseline of the element with the subscript-baseline of its parent.

`super`  
Aligns the baseline of the element with the superscript-baseline of its parent.

`text-top`  
Aligns the top of the element with the top of the parent element's font.

`text-bottom`  
Aligns the bottom of the element with the bottom of the parent element's font.

`middle`  
Aligns the middle of the element with the baseline plus half the x-height of the parent.

[`<length>`](length)  
Aligns the baseline of the element to the given length above the baseline of its parent. A negative value is allowed.

[`<percentage>`](percentage)  
Aligns the baseline of the element to the given percentage above the baseline of its parent, with the value being a percentage of the [`line-height`](line-height) property. A negative value is allowed.

#### Line-relative values

The following values vertically align the element relative to the entire line:

`top`  
Aligns the top of the element and its descendants with the top of the entire line.

`bottom`  
Aligns the bottom of the element and its descendants with the bottom of the entire line.

For elements that do not have a baseline, the bottom margin edge is used instead.

### Values for table cells

`baseline` (and `sub`, `super`, `text-top`, `text-bottom`, `<length>`, and `<percentage>`)  
Aligns the baseline of the cell with the baseline of all other cells in the row that are baseline-aligned.

`top`  
Aligns the top padding edge of the cell with the top of the row.

`middle`  
Centers the padding box of the cell within the row.

`bottom`  
Aligns the bottom padding edge of the cell with the bottom of the row.

Negative values are allowed.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>baseline</code></td></tr><tr class="even"><td>Applies to</td><td>inline-level and table-cell elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the <a href="line-height"><code>line-height</code></a> of the element itself</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>for percentage and length values, the absolute length, otherwise the keyword as specified</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    baseline | sub | super | text-top | text-bottom | middle | top | bottom | <percentage> | <length>

## Examples

### Basic example

#### HTML

    <div>An <img src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a default alignment.</div>
    <div>An <img class="top" src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a text-top alignment.</div>
    <div>An <img class="bottom" src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a text-bottom alignment.</div>
    <div>An <img class="middle" src="https://mdn.mozillademos.org/files/12245/frame_image.svg" alt="link" width="32" height="32" /> image with a middle alignment.</div>

#### CSS

    img.top { vertical-align: text-top; }
    img.bottom { vertical-align: text-bottom; }
    img.middle { vertical-align: middle; }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visudet.html#propdef-vertical-align">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'vertical-align' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds the <a href="length"><code>&lt;length&gt;</code></a> value and allows it to be applied to elements with a <a href="display"><code>display</code></a> type of <code>table-cell</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#vertical-align">CSS Level 1<br />
<span class="small">The definition of 'vertical-align' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`vertical-align`

1

12

1

4

4

1

1

18

4

14

1

1.0

## See also

- [Typical use cases of Flexbox, section "Center item"](css_flexible_box_layout/typical_use_cases_of_flexbox#center_item)
- [`line-height`](line-height), [`text-align`](text-align), [`margin`](margin)
- [Understanding `vertical-align`, or "How (Not) To Vertically Center Content"](http://phrogz.net/css/vertical-align/index.html)
- [Vertical-Align: All You Need To Know](https://christopheraue.net/design/vertical-align)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align</a>

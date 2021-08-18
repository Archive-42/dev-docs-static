# text-underline-offset

The `text-underline-offset` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the offset distance of an underline text decoration line (applied using [`text-decoration`](text-decoration)) from its original position.

`text-underline-offset` is not part of the [`text-decoration`](text-decoration) shorthand. While an element can have multiple `text-decoration` lines, `text-underline-offset` only impacts underlining, and **not** other possible line decoration options such as `overline` or `line-through`.

## Syntax

    /* Single keyword */
    text-underline-offset: auto;

    /* length */
    text-underline-offset: 0.1em;
    text-underline-offset: 3px;

    /* percentage */
    text-underline-offset: 20%;

    /* Global values */
    text-underline-offset: inherit;
    text-underline-offset: initial;
    text-underline-offset: unset;

The `text-underline-offset` property is specified as a single value from the list below.

### Values

`auto`  
The browser chooses the appropriate offset for underlines.

`<length>`  
Specifies the offset of underlines as a [`<length>`](length), overriding the font file suggestion and the browser default. It is recommended to use `em` units so the offset scales with the font size.

`<percentage>`  
Specifies the offset of underlines as a [`<percentage>`](percentage) of **1 em** in the element's font. A percentage inherits as a relative value, and so therefore scales with changes in the font. For a given application of this property, the offset is constant across the whole box that the underline is applied to, even if there are child elements with different font sizes or vertical alignment.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td>Percentages</td><td>refer to the font size of the element itself</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="even"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    auto | <length> | <percentage>

## Examples

### Demonstration of text-underline-offset

    <p class="oneline">Here's some text with an offset wavy red underline!</p>
    <br>
    <p class="twolines">This text has lines both above and below it. Only the bottom one is offset.</p>

    p {
      text-decoration: underline wavy red;
      text-underline-offset: 1em;
    }

    .twolines {
      text-decoration-color: purple;
      text-decoration-line: underline overline;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-4/#underline-offset">CSS Text Decoration Module Level 4<br />
<span class="small">The definition of 'text-underline-offset' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`text-underline-offset`

87

87

70

69

No

73

12.1

87

87

No

No

12.2

No

`percentage`

No

No

74

No

No

No

No

No

No

No

No

No

## See also

- [`text-decoration`](text-decoration)
- [`text-decoration-thickness`](text-decoration-thickness)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-offset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-offset</a>

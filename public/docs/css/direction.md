# direction

The `direction` CSS property sets the direction of text, table columns, and horizontal overflow. Use `rtl` for languages written from right to left (like Hebrew or Arabic), and `ltr` for those written from left to right (like English and most other languages).

Note that text direction is usually defined within a document (e.g., with [HTML's `dir` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/dir)) rather than through direct use of the `direction` property.

The property sets the base text direction of block-level elements and the direction of embeddings created by the [`unicode-bidi`](unicode-bidi) property. It also sets the default alignment of text, block-level elements, and the direction that cells flow within a table row.

Unlike the `dir` attribute in HTML, the `direction` property is not inherited from table columns into table cells, since CSS inheritance follows the document tree, and table cells are inside of rows but not inside of columns.

The `direction` and [`unicode-bidi`](unicode-bidi) properties are the two only properties which are not affected by the [`all`](all) shorthand property.

## Syntax

    /* Keyword values */
    direction: ltr;
    direction: rtl;

    /* Global values */
    direction: inherit;
    direction: initial;
    direction: unset;

### Values

`ltr`  
Text and other elements go from left to right. This is the default value.

`rtl`  
Text and other elements go from right to left.

For the `direction` property to have any effect on inline-level elements, the [`unicode-bidi`](unicode-bidi) property's value must be `embed` or `override`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>ltr</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    ltr | rtl

## Examples

### Setting right-to-left direction

In the example below are two strings of text, both which are displaying using `direction: rtl`. While the Arabic text is displayed correctly with this setting, the English text now has a full stop in an unusual location.

    blockquote {
      direction: rtl;
      width: 300px;
    }

    <blockquote>
    <p>This paragraph is in English but incorrectly goes right to left.<p>
    </blockquote>

    <blockquote>
    <p>هذه الفقرة باللغة العربية ، لذا يجب الانتقال من اليمين إلى اليسار.<p>
    </blockquote>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-writing-modes-3/#direction">CSS Writing Modes Module Level 3<br />
<span class="small">The definition of 'direction' in that specification.</span></a></td><td><span class="spec-pr">Proposed Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#direction">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'direction' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`direction`

2

12

1

5.5

9.2

1

1

18

4

10.1

1

1.0

## See also

- [`unicode-bidi`](unicode-bidi)
- [`writing-mode`](writing-mode)
- The HTML [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-dir) global attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/direction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/direction</a>

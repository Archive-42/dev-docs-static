# table-layout

The `table-layout` CSS property sets the algorithm used to lay out [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) cells, rows, and columns.

## Syntax

    /* Keyword values */
    table-layout: auto;
    table-layout: fixed;

    /* Global values */
    table-layout: inherit;
    table-layout: initial;
    table-layout: unset;

### Values

[`auto`](width)  
By default, most browsers use an automatic table layout algorithm. The widths of the table and its cells are adjusted to fit the content.

`fixed`  
Table and column widths are set by the widths of `table` and `col` elements or by the width of the first row of cells. Cells in subsequent rows do not affect column widths.

Under the "fixed" layout method, the entire table can be rendered once the first table row has been downloaded and analyzed. This can speed up rendering time over the "automatic" layout method, but subsequent cell content might not fit in the column widths provided. Cells use the [`overflow`](overflow) property to determine whether to clip any overflowing content, but only if the table has a known width; otherwise, they won't overflow the cells.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td><code>table</code> and <code>inline-table</code> elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | fixed

## Examples

### Fixed-width tables with text-overflow

This example uses a fixed table layout, combined with the [`width`](width) property, to restrict the table's width. The [`text-overflow`](text-overflow) property is used to apply an ellipsis to words that are too long to fit. If the table layout were `auto`, the table would grow to accommodate its contents, despite the specified `width`.

#### HTML

    <table>
      <tr><td>Ed</td><td>Wood</td></tr>
      <tr><td>Albert</td><td>Schweitzer</td></tr>
      <tr><td>Jane</td><td>Fonda</td></tr>
      <tr><td>William</td><td>Shakespeare</td></tr>
    </table>

#### CSS

    table {
      table-layout: fixed;
      width: 120px;
      border: 1px solid red;
    }

    td {
      border: 1px solid blue;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/tables.html#width-layout">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'table-layout' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`table-layout`

14

12

1

5

7

1

1.5

18

4

10.1

3

1.0

## See also

- `<table>`

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/table-layout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/table-layout</a>

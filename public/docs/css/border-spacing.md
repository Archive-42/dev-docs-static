# border-spacing

The `border-spacing` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the distance between the borders of adjacent [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) cells. This property applies only when [`border-collapse`](border-collapse) is `separate`.

The `border-spacing` value is also used along the outside edge of the table, where the distance between the table's border and the cells in the first/last column or row is the sum of the relevant (horizontal or vertical) `border-spacing` and the relevant (top, right, bottom, or left) [`padding`](padding) on the table.

**Note:** The `border-spacing` property is equivalent to the deprecated `cellspacing` `<table>` attribute, except that it has an optional second value that can be used to set different horizontal and vertical spacing.

## Syntax

    /* <length> */
    border-spacing: 2px;

    /* horizontal <length> | vertical <length> */
    border-spacing: 1cm 2em;

    /* Global values */
    border-spacing: inherit;
    border-spacing: initial;
    border-spacing: unset;

The `border-spacing` property may be specified as either one or two values.

- When **one** `<length>` value is specified, it defines both the horizontal and vertical spacings between cells.
- When **two** `<length>` values are specified, the first value defines the horizontal spacing between cells (i.e., the space between cells in adjacent _columns_), and the second value defines the vertical spacing between cells (i.e., the space between cells in adjacent _rows_).

### Values

[`<length>`](length)  
The size of the spacing as a fixed value.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td><code>table</code> and <code>inline-table</code> elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>two absolute lengths</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <length> <length>?

## Examples

### Spacing and padding table cells

This example applies a spacing of `.5em` vertically and `1em` horizontally between a table's cells. Note how, along its outside edges, the table's `padding` values are added to its `border-spacing` values.

#### HTML

    <table>
      <tr>
        <td>1</td><td>2</td><td>3</td>
      </tr>
      <tr>
        <td>4</td><td>5</td><td>6</td>
      </tr>
      <tr>
        <td>7</td><td>8</td><td>9</td>
      </tr>
    </table>

#### CSS

    table {
      border-spacing: 1em .5em;
      padding: 0 2em 1em 0;
      border: 1px solid orange;
    }

    td {
      width: 1.5em;
      height: 1.5em;
      background: #d2d2d2;
      text-align: center;
      vertical-align: middle;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/tables.html#separated-borders">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'border-spacing' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`border-spacing`

1

12

1

8

4

1

≤37

18

4

14

1

1.0

## See also

- [`border-collapse`](border-collapse), [`border-style`](border-style)
- The `border-spacing` property alters the appearance of the [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) HTML element.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing</a>

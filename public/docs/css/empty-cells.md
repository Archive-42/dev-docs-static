# empty-cells

The `empty-cells` CSS property sets whether borders and backgrounds appear around [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) cells that have no visible content.

This property has an effect only when the [`border-collapse`](border-collapse) property is `separate`.

## Syntax

    /* Keyword values */
    empty-cells: show;
    empty-cells: hide;

    /* Global values */
    empty-cells: inherit;
    empty-cells: initial;
    empty-cells: unset;

The `empty-cells` property is specified as one of the keyword values listed below.

### Values

`show`  
Borders and backgrounds are drawn like in normal cells.

`hide`  
No borders or backgrounds are drawn.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>show</code></td></tr><tr class="even"><td>Applies to</td><td>table-cell elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    show | hide

## Example

### Showing and hiding empty table cells

#### HTML

    <table class="table_1">
      <tr>
        <td>Moe</td>
        <td>Larry</td>
      </tr>
      <tr>
        <td>Curly</td>
        <td></td>
      </tr>
    </table>
    <br>
    <table class="table_2">
      <tr>
        <td>Moe</td>
        <td>Larry</td>
      </tr>
      <tr>
        <td>Curly</td>
        <td></td>
      </tr>
    </table>

#### CSS

    .table_1 {
      empty-cells: show;
    }

    .table_2 {
      empty-cells: hide;
    }

    td,
    th {
      border: 1px solid gray;
      padding: 0.5rem;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/tables.html#empty-cells">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'empty-cells' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`empty-cells`

1

12

1

8

4

1.2

1

18

4

10.1

3.1

1.0

## See also

- [`border-collapse`](border-collapse)
- [Styling tables](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Styling_tables)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/empty-cells" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/empty-cells</a>

# HTMLTableRowElement.insertCell()

The `HTMLTableRowElement.insertCell()` method inserts a new cell ([`<td>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td)) into a table row ([`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr)) and returns a reference to the cell.

**Note:** `insertCell()` inserts the cell directly into the row. The cell does not need to be appended separately with [`Node.appendChild()`](../node/appendchild) as would be the case if [`Document.createElement()`](../document/createelement) had been used to create the new `<td>` element.

You can not use `insertCell()` to create a new `<th>` element though.

## Syntax

    var newCell = HTMLTableRowElement.insertCell(index);

[`HTMLTableRowElement`](../htmltablerowelement) is a reference to an HTML [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) element.

### Parameters

`index` <span class="badge inline optional">Optional</span>  
`index` is the cell index of the new cell. If `index` is `-1` or equal to the number of cells, the cell is appended as the last cell in the row. If `index` is greater than the number of cells, an `IndexSizeError` exception will result. If `index` is omitted it defaults to `-1`.

### Return value

`newCell` is an [`HTMLTableCellElement`](../htmltablecellelement) that references the new cell.

## Example

This example uses [`HTMLTableElement.insertRow()`](../htmltableelement/insertrow) to append a new row to a table.

We then use `insertCell(0)` to insert a new cell in the new row. (To be valid HTML, a `<tr>` must have at least one `<td>` element.) Finally, we add some text to the cell using [`Document.createTextNode()`](../document/createtextnode) and [`Node.appendChild()`](../node/appendchild).

### HTML

    <table id="my-table">
      <tr><td>Row 1</td></tr>
      <tr><td>Row 2</td></tr>
      <tr><td>Row 3</td></tr>
    </table>

### JavaScript

    function addRow(tableID) {
      // Get a reference to the table
      let tableRef = document.getElementById(tableID);

      // Insert a row at the end of the table
      let newRow = tableRef.insertRow(-1);

      // Insert a cell in the row at index 0
      let newCell = newRow.insertCell(0);

      // Append a text node to the cell
      let newText = document.createTextNode('New bottom row');
      newCell.appendChild(newText);
    }

    // Call addRow() with the table's ID
    addRow('my-table');

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tables.html#dom-tr-insertcell">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableRowElement.insertCell()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-68927016">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLTableRowElement.insertCell()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`insertCell`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`negative_one_index_argument`

Yes

12

20

Yes

Yes

Yes

Yes

Yes

20

Yes

Yes

Yes

`optional_index_parameter`

Yes

12

20

Yes

Yes

Yes

Yes

Yes

20

Yes

Yes

Yes

## See also

- [`HTMLTableElement.insertRow()`](../htmltableelement/insertrow)
- The HTML element representing cells: [`HTMLTableCellElement`](../htmltablecellelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement/insertCell" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement/insertCell</a>

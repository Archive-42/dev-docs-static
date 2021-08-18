HTMLTableElement.insertRow()
============================

The `HTMLTableElement.insertRow()` method inserts a new row ([`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr)) in a given [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table), and returns a reference to the new row.

If a table has multiple [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) elements, by default, the new row is inserted into the last `<tbody>`. To insert the row into a specific `<tbody>`:

    let specific_tbody = document.getElementById(tbody_id);
    let row = specific_tbody.insertRow(index)

**Note:** `insertRow()` inserts the row directly into the table. The row does not need to be appended separately as would be the case if [`Document.createElement()`](../document/createelement) had been used to create the new `<tr>` element.

Syntax
------

    var newRow = HTMLTableElement.insertRow(index);

[`HTMLTableElement`](../htmltableelement) is a reference to an HTML [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) element.

### Parameters

 `index` <span class="badge inline optional">Optional</span>   
The row index of the new row. If `index` is `-1` or equal to the number of rows, the row is appended as the last row. If `index` is greater than the number of rows, an `IndexSizeError` exception will result. If `index` is omitted it defaults to `-1`.

### Return value

`newRow` is an [`HTMLTableRowElement`](../htmltablerowelement) that references the new row.

Example
-------

This example uses `insertRow(-1)` to append a new row to a table.

We then use [`HTMLTableRowElement.insertCell()`](../htmltablerowelement/insertcell) to insert a new cell in the new row. (To be valid HTML, a `<tr>` must have at least one `<td>` element.) Finally, we add some text to the cell using [`Document.createTextNode()`](../document/createtextnode) and [`Node.appendChild()`](../node/appendchild).

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tables.html#dom-table-insertrow">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement.insertRow()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-93995626">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLTableElement.insertRow()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Specifies in more detail where the row is inserted.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-39872903">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLTableElement.insertRow()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`insertRow`

1

12

1

Starting with Firefox 20, the index argument has been made optional and defaults to -1 as per HTML specification.

5.5

10

4

1

18

4

Starting with Firefox 20, the index argument has been made optional and defaults to -1 as per HTML specification.

10.1

3

1.0

See also
--------

-   [`HTMLTableRowElement.insertCell()`](../htmltablerowelement/insertcell)
-   The HTML element representing rows: [`HTMLTableRowElement`](../htmltablerowelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/insertRow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/insertRow</a>

# HTMLTableElement.deleteRow()

The `HTMLTableElement.deleteRow()` method removes a specific row ([`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr)) from a given [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table).

## Syntax

    HTMLTableElement.deleteRow(index)

### Parameters

`index`  
`index` is an integer representing the row that should be deleted.  
However, the special index `-1` can be used to remove the very last row of a table.

### Return value

No return value

### Errors thrown

If the number of the row to delete, specified by the parameter, is greater or equal to the number of available rows, or if it is negative and not equal to the special index `-1`, representing the last row of the table, the exception `INDEX_SIZE_ERR` is thrown.

## Example

This example uses JavaScript to delete a table's second row.

### HTML

    <table>
      <tr><td>Cell 1.1</td><td>Cell 1.2</td><td>Cell 1.3</td></tr>
      <tr><td>Cell 2.1</td><td>Cell 2.2</td><td>Cell 2.3</td></tr>
      <tr><td>Cell 3.1</td><td>Cell 3.2</td><td>Cell 3.3</td></tr>
    </table>

### JavaScript

    let table = document.querySelector('table');

    // Delete second row
    table.deleteRow(1);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-table-deleterow">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement: deleteRow' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`deleteRow`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/deleteRow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/deleteRow</a>

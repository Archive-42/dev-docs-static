# HTMLTableRowElement.rowIndex

The `HTMLTableRowElement.rowIndex` read-only property represents the position of a row in relation to the whole [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table).

Even when the [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead), [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody), and [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) elements are out of order in the HTML, browsers render the table in the right order. Therefore the rows count from `<thead>` to `<tbody>`, from `<tbody>` to `<tfoot>`.

## Syntax

    var index = HTMLTableRowElement.rowIndex

### Value

Returns the index of the row, or `-1` if the row is not part of a table.

## Example

This example uses JavaScript to label all the row numbers in a table.

### HTML

    <table>
      <thead>
        <tr><th>Item</th>        <th>Price</th></tr>
      </thead>
      <tbody>
        <tr><td>Bananas</td>     <td>$2</td></tr>
        <tr><td>Oranges</td>     <td>$8</td></tr>
        <tr><td>Top Sirloin</td> <td>$20</td></tr>
      </tbody>
      <tfoot>
        <tr><td>Total</td>       <td>$30</td></tr>
      </tfoot>
    </table>

### JavaScript

    let rows = document.querySelectorAll('tr');

    rows.forEach((row) => {
      let z = document.createElement("td");
      z.textContent = `(row #${row.rowIndex})`;
      row.appendChild(z);
    });

### Result

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

`rowIndex`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement/rowIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableRowElement/rowIndex</a>

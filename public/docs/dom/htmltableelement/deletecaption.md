# HTMLTableElement.deleteCaption()

The `HTMLTableElement.deleteCaption()` method removes the [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) element from a given [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table). If there is no `<caption>` element associated with the table, this method does nothing.

## Syntax

    HTMLTableElement.deleteCaption()

## Example

This example uses JavaScript to delete a table's caption.

### HTML

    <table>
      <caption>This caption will be deleted!</caption>
      <tr><td>Cell 1.1</td><td>Cell 1.2</td></tr>
      <tr><td>Cell 2.1</td><td>Cell 2.2</td></tr>
    </table>

### JavaScript

    let table = document.querySelector('table');
    table.deleteCaption();

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-table-deletecaption">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement: deleteCaption' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`deleteCaption`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/deleteCaption" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/deleteCaption</a>

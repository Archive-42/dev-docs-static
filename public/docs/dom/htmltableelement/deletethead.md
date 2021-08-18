# HTMLTableElement.deleteTHead()

The `HTMLTableElement.deleteTHead()` removes the [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead) element from a given [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table).

## Syntax

    HTMLTableElement.deleteTHead();

## Example

This example uses JavaScript to delete a table's header.

### HTML

    <table>
      <thead><th>Name</th><th>Occupation</th></thead>
      <tr><td>Bob</td><td>Plumber</td></tr>
      <tr><td>Jim</td><td>Roofer</td></tr>
    </table>

### JavaScript

    let table = document.querySelector('table');
    table.deleteTHead();

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-table-deletethead">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement: deleteTHead' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`deleteTHead`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/deleteTHead" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/deleteTHead</a>

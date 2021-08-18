# HTMLTableElement.rows

The read-only [`HTMLTableElement`](../htmltableelement) property `rows` returns a live [`HTMLCollection`](../htmlcollection) of all the rows in the table, including the rows contained within any [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead), [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot), and [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) elements.

Although the property itself is read-only, the returned object is live and allows the modification of its content.

## Syntax

    HTMLCollectionObject = table.rows;

### Value

An [`HTMLCollection`](../htmlcollection) providing a live-updating list of the [`HTMLTableRowElement`](../htmltablerowelement) objects representing all of the [`<tr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) elements contained in the table. This provides quick access to all of the table rows, without having to manually search for them.

## Example

    myrows = mytable.rows;
    firstRow = mytable.rows[0];
    lastRow = mytable.rows.item(mytable.rows.length-1);

This demonstrates how you can use both array syntax (line 2) and the [`HTMLCollection.item()`](../htmlcollection/item) method (line 3) to obtain individual rows in the table.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-table-rows">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement: rows' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`rows`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/rows" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/rows</a>

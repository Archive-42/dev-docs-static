# HTMLTableElement: createTFoot()

The `createTFoot()` method of [`HTMLTableElement`](../htmltableelement) objects returns the [`<tfoot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot) element associated with a given [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table). If no footer exists in the table, this method creates it, and then returns it.

**Note:** If no footer exists, `createTFoot()` inserts a new footer directly into the table. The footer does not need to be added separately as would be the case if [`Document.createElement()`](../document/createelement) had been used to create the new `<tfoot>` element.

## Syntax

    table.createTFoot();

### Return value

[`HTMLTableSectionElement`](../htmltablesectionelement)

## Example

    let myfoot = mytable.createTFoot();
    // Now this should be true: myfoot == mytable.tFoot

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-table-createtfoot">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement: createTFoot' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createTFoot`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/createTFoot" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/createTFoot</a>

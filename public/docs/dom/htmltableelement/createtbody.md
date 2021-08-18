# HTMLTableElement: createTBody()

The `createTBody()` method of [`HTMLTableElement`](../htmltableelement) objects creates and returns a new [`<tbody>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody) element associated with a given [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table).

**Note:** Unlike [`HTMLTableElement.createTHead()`](createthead) and [`HTMLTableElement.createTFoot()`](createtfoot), `createTBody()` systematically creates a new `<tbody>` element, even if the table already contains one or more bodies. If so, the new one is inserted after the existing ones.

## Syntax

    table.createTBody();

### Return value

[`HTMLTableSectionElement`](../htmltablesectionelement)

## Example

    let mybody = mytable.createTBody();
    // Now this should be true: mybody == mytable.tBodies.item(mytable.tBodies.length - 1)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-table-createtbody">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement: createTBody' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createTBody`

20

12

25

9

15

6

≤37

25

25

14

6

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/createTBody" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/createTBody</a>

HTMLTableElement: createTHead()
===============================

The `createTHead()` method of [`HTMLTableElement`](../htmltableelement) objects returns the [`<thead>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead) element associated with a given [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table). If no header exists in the table, this method creates it, and then returns it.

**Note:** If no header exists, `createTHead()` inserts a new header directly into the table. The header does not need to be added separately as would be the case if [`Document.createElement()`](../document/createelement) had been used to create the new `<thead>` element.

Syntax
------

    table.createTHead();

### Return value

[`HTMLTableSectionElement`](../htmltablesectionelement)

Example
-------

    let myhead = mytable.createTHead();
    // Now this should be true: myhead == mytable.tHead

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-table-createthead">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement: createTHead' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createTHead`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/createTHead" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/createTHead</a>

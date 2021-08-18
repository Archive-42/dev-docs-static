HTMLTableElement.createCaption()
================================

The `HTMLTableElement.createCaption()` method returns the [`<caption>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/caption) element associated with a given [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table). If no `<caption>` element exists on the table, this method creates it, and then returns it.

**Note:** If no caption exists, `createCaption()` inserts a new caption directly into the table. The caption does not need to be added separately as would be the case if [`Document.createElement()`](../document/createelement) had been used to create the new `<caption>` element.

Syntax
------

    HTMLTableElement = table.createCaption();

### Return value

[`HTMLTableCaptionElement`](../htmltablecaptionelement)

Example
-------

This example uses JavaScript to add a caption to a table that initially lacks one.

### HTML

    <table>
      <tr><td>Cell 1.1</td><td>Cell 1.2</td><td>Cell 1.3</td></tr>
      <tr><td>Cell 2.1</td><td>Cell 2.2</td><td>Cell 2.3</td></tr>
    </table>

### JavaScript

    let table = document.querySelector('table');
    let caption = table.createCaption();
    caption.textContent = 'This caption was created by JavaScript!';

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-table-createcaption">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTableElement: createCaption' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createCaption`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/createCaption" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement/createCaption</a>

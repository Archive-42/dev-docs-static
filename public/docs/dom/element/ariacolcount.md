# Element.ariaColCount

The `ariaColCount` property of the [`Element`](../element) interface reflects the value of the `aria-colcount` attribute, which defines the number of columns in a table, grid, or treegrid.

## Syntax

    var ariaColCount = element.ariaColCount;
    element.ariaColCount = ariaColCount

### Value

A [`DOMString`](../domstring).

## Examples

In this example the `aria-colcount` attribute on the element with an ID of `semantic-table` is set to "2". Using `ariaColCount` we update the value to "3".

    <table id="semantic-table" role="table" aria-label="Semantic Elements" aria-describedby="semantic_elements_table_desc" aria-rowcount="100" aria-colcount="2">
      <caption id="semantic_elements_table_desc">Semantic Elements to use instead of ARIA's roles</caption>
      <thead role="rowgroup">
        <tr role="row">
          <th role="columnheader" aria-sort="none" aria-rowindex="1">ARIA Role</th>
          <th role="columnheader" aria-sort="none" aria-rowindex="1">Semantic Element</th>
        </tr>
      </thead>
      <tbody role="rowgroup">
        <tr role="row">
          <td role="cell" aria-rowindex="11">header</td>
          <td role="cell" aria-rowindex="11">h1</td>
        </tr>
        <tr role="row">
          <td role="cell" aria-rowindex="16">header</td>
          <td role="cell" aria-rowindex="16">h6</td>
        </tr>
        <tr role="row">
          <td role="cell" aria-rowindex="18">rowgroup</td>
          <td role="cell" aria-rowindex="18">thead</td>
        </tr>
        <tr role="row">
          <td role="cell" aria-rowindex="24">term</td>
          <td role="cell" aria-rowindex="24">dt</td>
        </tr>
      </tbody>
    </table>

    let el = document.getElementById('semantic-table');
    console.log(el.ariaColCount); // 2
    el.ariaColCount = "3"
    console.log(el.ariaColCount); // 3

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariacolcount">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaColCount' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaColCount`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

- [ARIA: table role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Table_Role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColCount</a>

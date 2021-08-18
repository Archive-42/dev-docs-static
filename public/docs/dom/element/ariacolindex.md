Element.ariaColIndex
====================

The `ariaColIndex` property of the [`Element`](../element) interface reflects the value of the `aria-colindex` attribute, which defines an element's column index or position with respect to the total number of columns within a table, grid, or treegrid.

Syntax
------

    var ariaColIndex = element.ariaColIndex;
    element.ariaColIndex = ariaColIndex

### Value

A [`DOMString`](../domstring) which contains an integer.

Examples
--------

In this example the `aria-colindex` attribute on the element with an ID of `role-heading` is set to "1". Using `ariaColIndex` we update the value to "2".

    <table id="semantic-table" role="table" aria-label="Semantic Elements" aria-describedby="semantic_elements_table_desc" aria-rowcount="100">
      <caption id="semantic_elements_table_desc">Semantic Elements to use instead of ARIA's roles</caption>
      <thead role="rowgroup">
        <tr role="row">
          <th role="columnheader" id="role-heading" aria-sort="none" aria-rowindex="1" aria-colindex="1">ARIA Role</th>
          <th role="columnheader" id="element-heading" aria-sort="none" aria-rowindex="1">Semantic Element</th>
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

    let el = document.getElementById('role-heading');
    console.log(el.ariaColIndex); // 1
    el.ariaColIndex = "2"
    console.log(el.ariaColIndex); // 2

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariacolindex">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaColIndex' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaColIndex`

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

See also
--------

-   [ARIA: table role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Table_Role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColIndex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColIndex</a>

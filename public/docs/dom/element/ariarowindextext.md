Element.ariaRowIndexText
========================

The `ariaRowIndexText` property of the [`Element`](../element) interface reflects the value of the `aria-rowindextext` attribute, which defines a human readable text alternative of aria-rowindex.

Syntax
------

    var ariaRowIndexText = element.ariaRowIndexText;
    element.ariaRowIndexText = ariaRowIndexText

### Value

A [`DOMString`](../domstring).

Examples
--------

In this example the `aria-rowindextext` attribute on the element with an ID of `role-heading` is set to "Heading row". Using `ariaRowIndexText` we update the value to "Updated heading row".

    <table id="semantic-table" role="table" aria-label="Semantic Elements" aria-describedby="semantic_elements_table_desc" aria-rowcount="100">
      <caption id="semantic_elements_table_desc">Semantic Elements to use instead of ARIA's roles</caption>
      <thead role="rowgroup">
        <tr role="row">
          <th role="columnheader" id="role-heading" aria-sort="none" aria-rowindex="1" aria-rowindextext="Heading row">ARIA Role</th>
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
    console.log(el.ariaRowIndexText); // "Heading row"
    el.ariaRowIndexText = "Updated heading row"
    console.log(el.ariaRowIndexText); // "Updated heading row"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariarowindextext">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaRowIndexText' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.Element.ariaRowIndexText`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [ARIA: table role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Table_Role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowIndexText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowIndexText</a>
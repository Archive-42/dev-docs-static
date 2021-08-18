# Element.ariaSort

The `ariaSort` property of the [`Element`](../element) interface reflects the value of the `aria-sort` attribute, which indicates if items in a table or grid are sorted in ascending or descending order.

## Syntax

    var ariaSort = element.ariaSort;
    element.ariaSort = ariaSort

### Value

A [`DOMString`](../domstring) with one of the following values:

`"ascending"`  
Items are sorted in ascending order by this column.

`"descending"`  
Items are sorted in descending order by this column.

`"none"`  
There is no defined sort applied to the column.

`"other"`  
A sort algorithm other than ascending or descending has been applied.

## Examples

In this example the `aria-sort` attribute on the element with an ID of `role-heading` is set to "none". Using `ariaSort` we update the value to "ascending".

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
    console.log(el.ariaSort); // none
    el.ariaSort = "ascending"
    console.log(el.ariaSort); // ascending

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariasort">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaSort' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaSort`

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

## See also

- [ARIA: table role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Table_Role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSort</a>

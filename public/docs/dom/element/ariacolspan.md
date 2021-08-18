Element.ariaColSpan
===================

The `ariaColSpan` property of the [`Element`](../element) interface reflects the value of the `aria-colspan` attribute, which defines the number of columns spanned by a cell or gridcell within a table, grid, or treegrid.

Syntax
------

    var ariaColSpan = element.ariaColSpan;
    element.ariaColSpan = ariaColSpan

### Value

A [`DOMString`](../domstring) which contains an integer.

Examples
--------

In this example the `aria-colspan` attribute on the element with an ID of `spanning-heading` is set to "2". Using `ariaColSpan` we update the value to "3".

    <table>
      <tr>
        <th>Heading 1</th>
        <th>Heading 2</th>
        <th>Heading 3</td>
      </tr>
      <tr>
        <td colspan="2" aria-colspan="2" id="spanning-column">Spanning</td>
        <td>One</td>
      </tr>
    </table>

    let el = document.getElementById('spanning-column');
    console.log(el.ariaColSpan);
    el.ariaColSpan = "3";
    console.log(el.ariaColSpan);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariacolspan">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaColSpan' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaColSpan`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColSpan" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaColSpan</a>

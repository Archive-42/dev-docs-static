Element.ariaRowSpan
===================

The `ariaRowSpan` property of the [`Element`](../element) interface reflects the value of the `aria-rowspan` attribute, which defines the number of rows spanned by a cell or gridcell within a table, grid, or treegrid.

Syntax
------

    var ariaRowSpan = element.ariaRowSpan;
    element.ariaRowSpan = ariaRowSpan

### Value

A [`DOMString`](../domstring) which contains an integer.

Examples
--------

In this example the `aria-rowspan` attribute on the element with an ID of `spanning-heading` is set to "3". Using `ariaRowSpan` we update the value to "2".

    <table>
      <tr>
        <th id="spanning-heading" rowspan="3" aria-rowspan="3">Spanning heading</th>
        <th>Heading</th>
      </tr>
      <tr>
        <td>One</td>
      </tr>
      <tr>
        <td>Two</td>
      </tr>
    </table>

    let el = document.getElementById('spanning-heading');
    console.log(el.ariaRowSpan);
    el.ariaRowSpan = "2";
    console.log(el.ariaRowSpan);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariarowspan">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaRowSpan' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaRowSpan`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowSpan" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRowSpan</a>

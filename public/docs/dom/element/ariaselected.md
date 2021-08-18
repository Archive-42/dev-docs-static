Element.ariaSelected
====================

The `ariaSelected` property of the [`Element`](../element) interface reflects the value of the `aria-selected` attribute, which indicates the current "selected" state of elements that have a selected state.

Syntax
------

    var ariaSelected = element.ariaSelected;
    element.ariaSelected = ariaSelected

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
The item is selected.

`"false"`  
The item is not selected.

`"undefined"`  
The item is not

Examples
--------

In this example the `aria-selected` attribute on the element with an ID of `tab-id` is set to "true". Using `ariaSelected` we update the value to "false".

    <button role="tab" aria-selected="true" aria-controls="tabpanel-id" id="tab-id">Tab label</button>

    let el = document.getElementById('tab-id');
    console.log(el.ariaSelected); // true
    el.ariaSelected = "false";
    console.log(el.ariaSelected); // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariavaluemax">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaSelected' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaSelected`

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

-   [ARIA: tab role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Tab_Role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSelected" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaSelected</a>

Element.ariaLabel
=================

The `ariaLabel` property of the [`Element`](../element) interface reflects the value of the [`aria-label`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-label_attribute) attribute, which defines a string value that labels the current element.

Syntax
------

    var ariaLabel = element.ariaLabel;
    element.ariaLabel = ariaLabel

### Value

A [`DOMString`](../domstring).

Examples
--------

In this example the `aria-label` attribute on the element with an ID of `close-button` is set to "Close". Using `ariaLabel` we update the value to "Close dialog".

    <button aria-label="Close" id="close-button">X</button>

    let el = document.getElementById('close-button');
    console.log(el.ariaLabel); // "Close"
    el.ariaLabel = "Close dialog"
    console.log(el.ariaLabel); // "Close dialog"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-arialabel">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaLabel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaLabel`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLabel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLabel</a>

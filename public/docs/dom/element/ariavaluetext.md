Element.ariaValueText
=====================

The `ariaValueText` property of the [`Element`](../element) interface reflects the value of the [`aria-valuetext`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-valuetext_attribute) attribute, which defines the human readable text alternative of aria-valuenow for a range widget.

Syntax
------

    var ariaValueText = element.ariaValueText;
    element.ariaValueText = ariaValueText

### Value

A [`DOMString`](../domstring).

Examples
--------

In this example the `aria-valuetext` attribute on the element with an ID of `slider` is set to "Sunday" to give a human-readable value for the range. Using `ariaValueText` we update the value to "Monday".

    <div role="slider" aria-valuenow="1"
      aria-valuemin="1" aria-valuemax="7"
        aria-valuetext="Sunday">

    let el = document.getElementById('slider');
    console.log(el.ariaValueText); // Sunday
    el.ariaValueText = "Monday";
    console.log(el.ariaValueText); // Monday

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariavaluetext">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaValueText' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaValueText`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaValueText</a>

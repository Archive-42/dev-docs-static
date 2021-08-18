Element.ariaRequired
====================

### Note

The `ariaRequired` property of the [`Element`](../element) interface reflects the value of the `aria-required` attribute, which indicates that user input is required on the element before a form may be submitted.

Where possible use an HTML [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element with `type="text"` or a [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) as these have built in semantics and do not require ARIA attributes.

Syntax
------

    var ariaRequired = element.ariaRequired;
    element.ariaRequired = ariaRequired

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
Users need to provide input on an element before a form is submitted.

`"false"`  
User input is not necessary to submit the form.

Examples
--------

In this example the `aria-required` attribute on the element with an ID of `txtBoxInput` is set to "true" indicating that this input must be completed. Using `ariaRequired` we update the value to "false".

    <div id="txtboxMultilineLabel">Enter the tags for the article</div>
    <div role="textbox" id="txtBoxInput" contenteditable="true" aria-multiline="true"
      aria-labelledby="txtboxMultilineLabel" aria-required="true"></div>

    let el = document.getElementById('txtBoxInput');
    console.log(el.ariaRequired); // "true"
    el.ariaRequired = "false"
    console.log(el.ariaRequired); // "false"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariarequired">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaRequired' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaRequired`

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

-   [ARIA: textbox role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/textbox_role)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRequired" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaRequired</a>

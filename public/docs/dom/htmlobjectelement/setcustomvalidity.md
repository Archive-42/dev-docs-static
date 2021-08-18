HTMLObjectElement.setCustomValidity
===================================

The `setCustomValidity()` method of the [`HTMLObjectElement`](../htmlobjectelement) interface sets a custom validity message for the element.

Syntax
------

    HTMLObjectElement.setCustomValidity(message);

### Parameters

error  
The message to use for validity errors.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

None.

Examples
--------

In this example, we pass the ID of an input element, and set different error messages depending on whether the value is missing, too low or too high. Additionally you *must* call the [reportValidity](../htmlformelement/reportvalidity) method on the same element or nothing will happen.

    function validate(inputID)
    {
     var input = document.getElementById(inputID);
     var validityState_object = input.validity;

     if (validityState_object.valueMissing)
     {
      input.setCustomValidity('You gotta fill this out, yo!');
      input.reportValidity();
     }
     else if (validityState_object.rangeUnderflow)
     {
      input.setCustomValidity('We need a higher number!');
      input.reportValidity();
     }
     else if (validityState_object.rangeOverflow)
     {
      input.setCustomValidity('Thats too high!');
      input.reportValidity();
     }
     else
     {
      input.setCustomValidity('');
      input.reportValidity();
     }
    }

It's vital to set the message to an empty string if there are no errors. As long as the error message is not null, the form will not pass validation and will not be submitted.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-cva-setcustomvalidity">HTML Living Standard<br />
<span class="small">The definition of 'setCustomValidity' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setCustomValidity`

10

12

4

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

See also
--------

-   [`validityState`](../validitystate)
-   <span class="page-not-created">`validityState.valueMissing`</span>
-   [`validityState.typeMismatch`](../validitystate/typemismatch)
-   [`validityState.patternMismatch`](../validitystate/patternmismatch)
-   [`validityState.tooLong`](../validitystate/toolong)
-   [`validityState.tooShort`](../validitystate/tooshort)
-   [`validityState.rangeUnderflow`](../validitystate/rangeunderflow)
-   [`validityState.rangeOverflow`](../validitystate/rangeoverflow)
-   [`validityState.stepMismatch`](../validitystate/stepmismatch)
-   <span class="page-not-created">`validityState.valid`</span>
-   <span class="page-not-created">`validityState.customError`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement/setCustomValidity" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement/setCustomValidity</a>

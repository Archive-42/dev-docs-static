# PayerErrors.phone

**Draft**

This page is not complete.

The `phone` property is found in a [`PayerErrors`](../payererrors) object if the [`payerName`](../paymentresponse/payerphone) returned in the response couldn't be validated as a valid phone number. The value of this property is a string explaining the problem. If the payer's phone number validated successfully, the `phone` property is omitted from the `PayerErrors` object.

## Syntax

    payerPhone = payerErrors.phone;

### Value

If this property is present in the [`PayerErrors`](../payererrors) object, the payer's phone number couldn't be successfully validated, and the `phone` property's value is a [`DOMString`](../domstring) explaining the error. This string will be displayed to the user by the [user agent's](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) payment handling user interface as appropriate.

If the phone number is valid, this property is omitted from the [`PayerErrors`](../payererrors) object.

## Example

    function validatePayment(response) {
      const correctionPromises
      let paymentErrors = {};
      let payerErrors = {};

      // Check payer details

      if (!validEmail(response.payerEmail)) {
        payerErrors.email = "Please make sure you enter a valid email address."
      }
      if (!validName(response.payerName)) {
        payerErrors.email = "Please enter a valid name, using only <appropriate characters>."
      }
      if (!validPhone(response.payerPhone)) {
        payerErrors.phone = "Please enter a valid phone number in the form ###-###-####."
      }

      // Check everything else too...

      //
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-payererrors-phone">Payment Request API<br />
<span class="small">The definition of 'PayerErrors.phone' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`phone`

71

69-71

≤79

64

Enabled by default in nightly US English builds of Firefox 64 and later, and on other localizations when geolocation indicates the user is in the United States or Canada.

56

No

No

?

No

71

69-71

64

Enabled by default in nightly US English builds of Firefox 64 and later, and on other localizations when geolocation indicates the user is in the United States or Canada.

56

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PayerErrors/phone" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PayerErrors/phone</a>

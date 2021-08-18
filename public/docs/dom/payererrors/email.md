# PayerErrors.email

**Draft**

This page is not complete.

The `email` property is included in a [`PayerErrors`](../payererrors) object if the [`PaymentResponse.payerEmail`](../paymentresponse/payeremail) property failed validation; in this case, the property should contain a string describing how to correct the problem. If the payer's email address passed validation, this property is not included in the `PayerErrors` object.

## Syntax

    payerEmail = payerErrors.email;

### Value

If validation of the payer's email address ([`PaymentResponse.payerEmail`](../paymentresponse/payeremail)) found problems, this property should be set to a [`DOMString`](../domstring) that explains the validation problem and how to correct it. If the email address is valid, this property should be omitted from the [`PayerErrors`](../payererrors) object.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-payererrors-email">Payment Request API<br />
<span class="small">The definition of 'PayerErrors.email' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`email`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PayerErrors/email" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PayerErrors/email</a>

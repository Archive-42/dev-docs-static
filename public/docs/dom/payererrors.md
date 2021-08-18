# PayerErrors

The `PayerErrors` dictionary is used by the [Payment Request API](payment_request_api) to indicate the presence of—and to explain how to correct—validation errors in the payer details. For each field in the payment information that fails validation, the `PayerErrors` object contains a string explaining the error.

The payer details include the payer's name, phone number, and email address.

## Properties

[`email`](payererrors/email) <span class="badge inline optional">Optional</span>  
If present, this [`DOMString`](domstring) is a string describing the validation error from which the payer's email address—as given by [`PaymentResponse.payerEmail`](paymentresponse/payeremail)—currently suffers. If this property is absent from the `PayerErrors` object, the email address passed validation.

[`name`](payererrors/name) <span class="badge inline optional">Optional</span>  
If this [`DOMString`](domstring) is present in the object, the [`PaymentResponse.payerName`](paymentresponse/payername) property failed validation, and this string explains what needs to be corrected. If this property is absent, the paer name is fine

[`phone`](payererrors/phone) <span class="badge inline optional">Optional</span>  
If present, this string is an error message explaining why the payer's phone number ([`PaymentResponse.payerPhone`](paymentresponse/payerphone)) failed validation. This property is absent if the phone number passed validation.

## Example

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-payererrors">Payment Request API<br />
<span class="small">The definition of 'PayerErrors' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PayerErrors`

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

`name`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PayerErrors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PayerErrors</a>

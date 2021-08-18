# PaymentResponse.payerEmail

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `payerEmail` read-only property of the [`PaymentResponse`](../paymentresponse) interface returns the email address supplied by the user. This option is only present when the `requestPayerEmail` option is set to `true` in the <span class="page-not-created">`PaymentOptions`</span> object passed to the [`PaymentRequest`](../paymentrequest/paymentrequest) constructor.

## Syntax

    var payerEmail = PaymentResponse.payerEmail;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/">Payment Request API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`payerEmail`

60

15

No

Available only in nightly builds.

No

47

11.1

No

56

No

Available only in nightly builds.

43

11.3

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/payerEmail" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/payerEmail</a>

# PaymentValidationErrors

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PaymentValidationErrors` dictionary represents objects providing information about any and all errors that occurred while processing a payment request. When validation of the [`PaymentResponse`](paymentresponse) returned by the [`PaymentRequest.show()`](paymentrequest/show) or [`PaymentResponse.retry()`](paymentresponse/retry) methods fails, your code creates a `PaymentValidationErrors` object to pass into `retry()` so that the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) knows what needs to be fixed and what if any error messages to display to the user.

## Properties

<span class="page-not-created">`error`</span> <span class="badge inline optional">Optional</span>  
A general description of a payment error from which the user may attempt to recover by retrying the payment, possibly after correcting mistakes in the payment information. `error` can be provided all by itself to provide only a generic error message, or in concert with the other properties to serve as an overview while other properties' values gude the user to errors in specific fields in the payment form.

<span class="page-not-created">`payer`</span> <span class="badge inline optional">Optional</span>  
A [`PayerErrors`](payererrors) compliant object which provides appropriate error messages for any of the fields describing the payer which failed validation.

<span class="page-not-created">`paymentMethod`</span> <span class="badge inline optional">Optional</span>  
Any payment method specific errors which may have occurred. This object's contents will vary depending on the payment used. For example, if the user chose to pay by credit card using the `basic-card` payment method, this is a <span class="page-not-created">`BasicCardErrors`</span> object.

<span class="page-not-created">`shippingAddress`</span> <span class="badge inline optional">Optional</span>  
An [`AddressErrors`](addresserrors) object which contains error messages for any of the fields in the shipping address that failed validation.

## Example

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/">Payment Request API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/payment-method-basic-card/">Basic Card Payment</a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines <span class="page-not-created"><code>BasicCardErrors</code></span></td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.PaymentValidationErrors`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Payment Request API](payment_request_api)
- [Using the Payment Request API](payment_request_api/using_the_payment_request_api)
- [Payment processing concepts](payment_request_api/concepts)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentValidationErrors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentValidationErrors</a>

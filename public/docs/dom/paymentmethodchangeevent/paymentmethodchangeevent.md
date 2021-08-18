# PaymentMethodChangeEvent

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PaymentMethodChangeEvent()` constructor creates a new [`PaymentMethodChangeEvent`](../paymentmethodchangeevent) object providing details about a `paymentmethodchange` event.

## Syntax

    paymentMethodChangeEvent = new PaymentMethodChangeEvent(type, options);

### Parameters

`type`  
A [`DOMString`](../domstring) which must contain the string `paymentmethodchange`, the name of the only type of event which uses the `PaymentMethodChangeEvent` interface.

`options` <span class="badge inline optional">Optional</span>  
An optional <span class="page-not-created">`PaymentMethodChangeEventInit`</span> dictionary which may contain zero or more of the following properties:

`methodName` <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) containing the payment method identifier for the payment handler being used. This is an empty string by default.

`methodDetails` <span class="badge inline optional">Optional</span>  
An object providing payment method-specific information describing the changes made to the payment, or `null` if there is no additional information available or required. This is `null` by default.

### Return value

A newly-created [`PaymentMethodChangeEvent`](../paymentmethodchangeevent) object describing a change to the options specified for the payment method given in the `methodName` property.

The type of the `methodDetails` property depends on the payment method. For example, if `methodName` is `basic-card`, indicating that the basic card payment method is being used for validation, the `methodDetails` field must be a <span class="page-not-created">`BasicCardChangeDetails`</span> object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#paymentmethodchangeevent-interface">Payment Request API<br />
<span class="small">The definition of 'PaymentMethodChangeEvent()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.PaymentMethodChangeEvent.PaymentMethodChangeEvent`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Payment Request API](../payment_request_api)
- [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
- [Payment processing concepts](../payment_request_api/concepts)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentMethodChangeEvent/PaymentMethodChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentMethodChangeEvent/PaymentMethodChangeEvent</a>

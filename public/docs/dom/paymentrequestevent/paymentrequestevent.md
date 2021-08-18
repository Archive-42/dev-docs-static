# PaymentRequestEvent()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `PaymentRequestEvent` constructor creates a new [`PaymentRequestEvent`](../paymentrequestevent) object which is a constructor for a [`PaymentRequestEvent`](../paymentrequestevent) which is the object passed to a payment handler when a [`PaymentRequest`](../paymentrequest) is made..

## Syntax

    var paymentRequestEvent = new PaymentRequestEventy(type, options)

### Parameters

_type_  
Must always be `'PaymentRequest'`.

_options_ <span class="badge inline optional">Optional</span>  
Options are as follows:

- `instrumentKey`: A <span class="page-not-created">`PaymentInstrument`</span> object reflecting the payment instrument selected by the user or an empty string if the user has not registered or chosen a payment instrument.
- `methodData`: An array of <span class="page-not-created">`PaymentMethodData`</span> objects containing payment method identifers for the payment methods that the web site accepts and any associated payment method specific data.
- `modifiers`: An array of objects containing changes to payment details.
- `paymentRequestId`: The ID of the [`PaymentRequest`](../paymentrequest) object.
- `paymentRequestOrigin`: The origin where the [`PaymentRequest`](../paymentrequest) object was initialized.
- `topLeveOrigin`: The top-level origin where the [`PaymentRequest`](../paymentrequest) object was initialized.
- `total`: The total amount being requested for payment.

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

`PaymentRequestEvent`

70

79

No

No

57

No

No

70

No

49

No

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/PaymentRequestEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestEvent/PaymentRequestEvent</a>

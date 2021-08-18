# PaymentMethodChangeEvent

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PaymentMethodChangeEvent` interface of the [Payment Request API](payment_request_api) describes the [`paymentmethodchange`](paymentrequest/paymentmethodchange_event) event which is fired by some payment handlers when the user switches payment instruments (e.g., a user selects a "store" card to make a purchase while using Apple Pay).

## Constructor

[`PaymentMethodChangeEvent()`](paymentmethodchangeevent/paymentmethodchangeevent)  
Creates and returns a new `PaymentMethodChangeEvent` object, optionally initialized with values taken from a given <span class="page-not-created">`PaymentMethodChangeEventInit`</span> dictionary.

## Properties

_In addition to the properties below, this interface includes properties inherited from [`PaymentRequestUpdateEvent`](paymentrequestupdateevent)._

[`methodDetails`](paymentmethodchangeevent/methoddetails) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>  
An object containing payment method-specific data useful when handling a payment method change. If no such information is available, this value is `null`.

[`methodName`](paymentmethodchangeevent/methodname) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>  
A [`DOMString`](domstring) containing the payment method identifier, a string which uniquely identifies a particular payment method. This identifier is usually a URL used during the payment process, but may be a standardized non-URL string as well, such as `basic-card`. The default value is the empty string, `""`.

## Methods

_This interface includes methods inherited from [`PaymentRequestUpdateEvent`](paymentrequestupdateevent)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#paymentmethodchangeevent-interface">Payment Request API<br />
<span class="small">The definition of 'PaymentMethodChangeEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentMethodChangeEvent`

76

79

No

Available only in nightly builds. Requires `dom.payments.request.enabled` to be set to `true` and the comma-delineated list in `dom.payments.request.supportedRegions` to contain one or more of the supported 2-character ISO locales, currently US and CA.

No

63

12.1

No

76

No

Available only in nightly builds. Requires `dom.payments.request.enabled` to be set to `true` and the comma-delineated list in `dom.payments.request.supportedRegions` to contain one or more of the supported 2-character ISO locales, currently US and CA.

54

12.2

Yes

`methodDetails`

76

79

No

No

63

12.1

No

76

No

54

12.2

Yes

`methodName`

76

79

No

No

63

12.1

No

76

No

54

12.2

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentMethodChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentMethodChangeEvent</a>

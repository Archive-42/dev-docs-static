PaymentRequest
==============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [Payment Request API's](payment_request_api) `PaymentRequest` interface the primary access point into the API, and lets web content and apps accept payments from the end user on behalf of the operator of the site or the publisher of the app.

Constructor
-----------

 [`PaymentRequest()`](paymentrequest/paymentrequest) <span class="notecard inline secure">Secure context</span>   
Creates a new `PaymentRequest` object.

Properties
----------

 [`PaymentRequest.id`](paymentrequest/id) <span class="badge inline readonly">Read only </span><span class="notecard inline secure">Secure context</span>   
An unique identifier for a particular `PaymentRequest`, which can be set via `details.id`. When none is set, it defaults to a UUID.

 [`PaymentRequest.shippingAddress`](paymentrequest/shippingaddress) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
If requested via payment options, returns the shipping address chosen by the user for the purposes of calculating shipping. This property is only populated if the constructor is called with the `requestShipping` flag set to true. Additionally, in some browsers, the parts of the address will be redacted for privacy until the user indicates they are ready to complete the transaction (i.e., they hit "Pay").

 [`PaymentRequest.shippingOption`](paymentrequest/shippingoption) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns the identifier of the selected shipping option. This property is only populated if the constructor is called with the `requestShipping` flag set to true.

 [`PaymentRequest.shippingType`](paymentrequest/shippingtype) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>   
Returns the type of shipping used to fulfill the transaction. This will be one of `shipping`, `delivery`, `pickup`, or `null` if a value was not provided in the constructor.

Methods
-------

 [`PaymentRequest.canMakePayment()`](paymentrequest/canmakepayment) <span class="notecard inline secure">Secure context</span>   
Indicates whether the `PaymentRequest` object can make a payment before calling `show()`.

 [`PaymentRequest.show()`](paymentrequest/show) <span class="notecard inline secure">Secure context</span>   
Causes the user agent to begin the user interaction for the payment request.

 [`PaymentRequest.abort()`](paymentrequest/abort) <span class="notecard inline secure">Secure context</span>   
Causes the user agent to end the payment request and to remove any user interface that might be shown.

Events
------

 [`merchantvalidation`](paymentrequest/merchantvalidation_event) <span class="notecard inline secure">Secure context</span>   
With some payment handlers (e.g., Apple Pay), this event handler is called to handle the `merchantvalidation` event, which is dispatched when the user agent requires that the merchant validate that the merchant or vendor requesting payment is legitimate.  
Also available using the [`onmerchantvalidation`](paymentrequest/onmerchantvalidation) event handler property.

 [`paymentmethodchange`](paymentrequest/paymentmethodchange_event) <span class="notecard inline secure">Secure context</span>   
With some payment handlers (e.g., Apple Pay), dispatched whenever the user changes payment instrument, like switching from a credit card to a debit card.  
Also available using the [`onpaymentmethodchange`](paymentrequest/onpaymentmethodchange) event handler property.

 [`shippingaddresschange`](paymentrequest/shippingaddresschange_event) <span class="notecard inline secure">Secure context</span>   
Dispatched whenever the user changes their shipping address.  
Also available using the [`onshippingaddresschange`](paymentrequest/onshippingaddresschange) event handler property.

 [`shippingoptionchange`](paymentrequest/shippingoptionchange_event) <span class="notecard inline secure">Secure context</span>   
Dispatched whenever the user changes a shipping option.  
Also available using the [`onshippingoptionchange`](paymentrequest/onshippingoptionchange) event handler property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#paymentrequest-interface">Payment Request API<br />
<span class="small">The definition of 'PaymentRequest' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentRequest`

60

15

No

Available only in nightly builds. Requires `dom.payments.request.enabled` to be set to `true` and the comma-delineated list in `dom.payments.request.supportedRegions` to contain one or more of the supported 2-character ISO locales, currently US and CA.

No

47

11.1

No

53

No

Available only in nightly builds. Requires `dom.payments.request.enabled` to be set to `true` and the comma-delineated list in `dom.payments.request.supportedRegions` to contain one or more of the supported 2-character ISO locales, currently US and CA.

44

11.3

6.0

`PaymentRequest`

60

15

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

`abort`

60

15

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

`canMakePayment`

60

16

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

`id`

60

16

No

Available only in nightly builds.

No

47

11.1

No

60

No

Available only in nightly builds.

44

11.3

8.0

`merchantvalidation_event`

?

?

No

Available only in nightly builds.

No

?

?

No

?

No

Available only in nightly builds.

?

?

?

`onmerchantvalidation`

No

No

No

Available only in nightly builds.

No

No

11.1

No

No

No

Available only in nightly builds.

No

11.3

No

`onpaymentmethodchange`

76

79

No

Available only in nightly builds.

No

47

12.1

No

Yes

No

Available only in nightly builds.

44

12.2

Yes

`onshippingaddresschange`

60

15

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

`onshippingoptionchange`

60

15

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

`paymentmethodchange_event`

No

No

No

Available only in nightly builds.

No

No

No

No

No

No

Available only in nightly builds.

No

No

No

`requestId`

No

≤18-79

No

Available only in nightly builds.

No

No

?

No

No

No

Available only in nightly builds.

No

?

No

`shippingAddress`

61

15

No

No

47

No

No

53

No

44

No

6.0

`shippingaddresschange_event`

61

15

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

`shippingOption`

60

15

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

`shippingoptionchange_event`

61

15

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

`shippingType`

60

15

No

Available only in nightly builds.

No

47

11.1

No

55

No

Available only in nightly builds.

44

11.3

6.0

`show`

60

15

No

Available only in nightly builds.

No

47

11.1

No

53

No

Available only in nightly builds.

44

11.3

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest</a>

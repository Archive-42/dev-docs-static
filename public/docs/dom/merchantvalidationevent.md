MerchantValidationEvent
=======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `MerchantValidationEvent` interface of the [Payment Request API](payment_request_api) enables a merchant to verify themselves as allowed to use a particular payment handler.

To learn more about merchant validation, see [Merchant validation](payment_request_api/concepts#merchant_validation) in [Payment processing concepts](payment_request_api/concepts).

Constructor
-----------

 [`MerchantValidationEvent()`](merchantvalidationevent/merchantvalidationevent) <span class="notecard inline secure">Secure context</span>   
Creates a new `MerchantValidationEvent` object describing a `merchantvalidation` event that will be sent to the payment handler to request that it validate the merchant.

Properties
----------

 [`MerchantValidationEvent.methodName`](merchantvalidationevent/methodname) <span class="notecard inline secure">Secure context</span>   
A [`DOMString`](domstring) providing a unique payment method identifier for the payment handler that's requiring validation. This may be either one of the standard payment method identifier strings or a URL that both identifies and handles requests for the payment handler, such as `https://apple.com/apple-pay`.

 [`MerchantValidationEvent.validationURL`](merchantvalidationevent/validationurl) <span class="notecard inline secure">Secure context</span>   
A [`USVString`](usvstring) specifying a URL from which the site or app can fetch payment handler specific validation information. Once this data is retrieved, the data (or a promise resolving to the validation data) should be passed into [`complete()`](merchantvalidationevent/complete) to validate that the payment request is coming from an authorized merchant.

Methods
-------

 [`MerchantValidationEvent.complete()`](merchantvalidationevent/complete) <span class="notecard inline secure">Secure context</span>   
Pass the data retrieved from the URL specified by [`validationURL`](merchantvalidationevent/validationurl) into `complete()` to complete the validation process for the [`PaymentRequest`](paymentrequest).

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

`MerchantValidationEvent`

No

No

64

Available only in Nightly builds.

No

No

11.1

No

No

64

Available only in Nightly builds.

No

11.3

No

`MerchantValidationEvent`

No

No

64

Available only in Nightly builds.

No

No

12.1

No

No

64

Available only in Nightly builds.

No

12.2

No

`complete`

No

No

64

Available only in Nightly builds.

No

No

11.1

No

No

64

Available only in Nightly builds.

No

11.3

No

`methodName`

No

No

64

Available only in Nightly builds.

No

No

12.1

No

No

64

Available only in Nightly builds.

No

12.2

No

`validationURL`

No

No

64

Available only in Nightly builds.

No

No

11.1

No

No

64

Available only in Nightly builds.

No

11.3

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MerchantValidationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MerchantValidationEvent</a>

MerchantValidationEvent.validationURL
=====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`MerchantValidationEvent`](../merchantvalidationevent) property `validationURL` is a read-only string value providing the URL from which to fetch the payment handler-specific data needed to validate the merchant.

This data should be passed into the [`complete()`](complete) method to let the user agent complete the transaction.

Syntax
------

    validationURL = merchantValidationEvent.validationURL;

### Value

A read-only [`USVString`](../usvstring) giving the URL from which to load payment handler specific data needed to complete the merchant verification process. Once this has been loaded, it should be passed into [`complete()`](complete), either directly or using a promise.

See [Merchant validation](#) in [Payment processing concepts](../payment_request_api/concepts) for more information on the merchant validation process.

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

See also
--------

-   [Payment Request API](../payment_request_api)
-   [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
-   [Payment processing concepts](../payment_request_api/concepts)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MerchantValidationEvent/validationURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MerchantValidationEvent/validationURL</a>

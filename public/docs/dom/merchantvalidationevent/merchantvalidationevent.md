MerchantValidationEvent()
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `MerchantValidationEvent()` constructor creates a new [`MerchantValidationEvent`](../merchantvalidationevent) object. You should not have to create these events yourself; instead, just handle the `merchantvalidation` event.

Syntax
------

    merchantValidationEvent = new MerchantValidationEvent(type, options);

### Parameters

`type`  
A [`DOMString`](../domstring) which must be `merchantvalidation`, the only type of event which uses the `MerchantValidationEvent` interface.

 `options` <span class="badge inline optional">Optional</span>   
An optional dictionary which may contain zero or more of the following properties:

 `methodName` <span class="badge inline optional">Optional</span>   
A [`DOMString`](../domstring) containing the payment method identifier for the payment handler being used. This is an empty string by default.

 `validationURL` <span class="badge inline optional">Optional</span>   
The URL from which to retrieve payment handler specific verification information used to validate the merchant. This is an empty string by default.

### Return value

A newly-created [`MerchantValidationEvent`](../merchantvalidationevent) providing the information that needs to be delivered to the client-side code to present to the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) by calling [`complete()`](complete).

### Exceptions

`TypeError`  
The string specified as `validationURL` could not be parsed as a URL.

`RangeError`  
The specified `methodName` does not correspond to a known and supported merchant or is not a well-formed standard payment method identifier.

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

12.1

No

No

64

Available only in Nightly builds.

No

12.2

No

See also
--------

-   [Payment Request API](../payment_request_api)
-   [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
-   [Payment processing concepts](../payment_request_api/concepts)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MerchantValidationEvent/MerchantValidationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MerchantValidationEvent/MerchantValidationEvent</a>

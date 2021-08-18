PaymentRequest.onmerchantvalidation
===================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentRequest`](../paymentrequest) event handler `onmerchantvalidation` is invoked when the `merchantvalidation` is fired, indicating that the payment handler (e.g., Apple Pay) requires the merchant to validate themselves. This is usually the first event to be fired, and the user won't be able to proceed with a payment until the merchant validate themselves.

This event is not be fired by all payment handlers. In particular, it's used by Apple Pay.

Syntax
------

    paymentRequest.onmerchantvalidation = eventHandlerFunction;

### Value

An event handler function which is to be called whenever the `merchantvalidation` event is fired at the [`PaymentRequest`](../paymentrequest), indicating that the payment handler requires the merchant to validate themselves as allowed to use this payment handler.

Examples
--------

An example merchant validation handler for the [`PaymentRequest`](../paymentrequest) object `request` looks like this:

    request.onmerchantvalidation = ev => {
      ev.complete(async () => {
        const merchantServerUrl = window.location.origin +
            '/validation?url=' + encodeURIComponent(ev.validationURL);
        // get validation data, and complete validation;
        return await fetch(merchantServerUrl).then(r => r.text());
      })
    };

    const response = await request.show();

For more information, see [Merchant Validation](#) in [Payment processing concepts](../payment_request_api/concepts).

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/onmerchantvalidation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/onmerchantvalidation</a>

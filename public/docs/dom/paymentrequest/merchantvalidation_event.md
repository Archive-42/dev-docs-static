PaymentRequest: merchantvalidation event
========================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`merchantvalidation` events are delivered by the [Payment Request API](../payment_request_api) to a [`PaymentRequest`](../paymentrequest) object when a payment handler requires that the merchant requesting the purchase validate itself as permitted to use the payment handler.

See [Merchant validation](../payment_request_api/concepts#merchant_validation) in [Payment processing concepts](../payment_request_api/concepts) for details on how the merchant validation process works.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../merchantvalidationevent"><code>MerchantValidationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onmerchantvalidation"><code>onmerchantvalidation</code></a></td></tr></tbody></table>

Examples
--------

In this example, an event handler is established for the `merchantvalidation` event. It uses the [`fetch()`](../windoworworkerglobalscope/fetch) to send a request to its own server with an argument of the payment method's validation URL, obtained from the event's [`validationURL`](../merchantvalidationevent/validationurl) property. The merchant server should access the validation URL in accordance with the payment method documention. Typically, a client should not access the validation URL.

    request.addEventListener("merchantvalidation", event => {
      event.complete(async () => {
        const merchantServerUrl = window.location.origin +
            '/validate?url=' + encodeURIComponent(event.validationURL);
        // get validation data, and complete validation;
        return await fetch(merchantServerUrl).then(response => response.text());
      }, false);
    };

    const response = await request.show();

How merchant server handles the validation depends on the server implementation and payment method documentation. The content delivered by the validation server is forwarded to the merchant server and is then returned from the `fetch()` call's fulfillment handler to the [`complete()`](../merchantvalidationevent/complete) method on the event. This response lets the payment handler know if the merchant is validated.

You can also use the [`onmerchantvalidation`](onmerchantvalidation) event handler property to set up the handler for this event:

    request.onmerchantvalidation = event => {
      event.complete(async () => {
        const merchantServerUrl = window.location.origin +
            '/validate?url=' + encodeURIComponent(event.validationURL);
        // get validation data, and complete validation;
        return await fetch(merchantServerUrl).then(response => response.text());
      });
    };

    const response = await request.show();

For more information, see [Merchant Validation](../payment_request_api/concepts#merchant_validation) in [Payment processing concepts](../payment_request_api/concepts).

Related events
--------------

-   `payerdetailchange`, `paymentmethodchange`, `shippingaddresschange`, and `shippingoptionchange`

BCD tables only load in the browser

-   [Payment Request API](../payment_request_api)
-   [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
-   [`onmerchantvalidation`](onmerchantvalidation) event handler property
-   [Merchant validation](../payment_request_api/concepts#merchant_validation) in [Payment processing concepts](../payment_request_api/concepts)
-   [`PaymentRequest`](../paymentrequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/merchantvalidation_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequest/merchantvalidation_event</a>

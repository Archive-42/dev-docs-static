PaymentResponse.methodName
==========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `methodName` read-only property of the [`PaymentResponse`](../paymentresponse) interface returns a string uniquely identifying the payment handler selected by the user. This string may be either one of the standardized payment method identifiers or a URL used by the payment handler to process payments.

Syntax
------

    var methodName = PaymentResponse.methodName;

### Value

A [`DOMString`](../domstring) uniquely identifying the payment handler being used to process the payment. This may be either a standardized identifier, or a URL used by the payment processor to handle payments. See [Merchant validation](#) in [Payment processing concepts](../payment_request_api/concepts) for more information.

Example
-------

The following example extracts the method name from the [`PaymentResponse`](../paymentresponse) object to the promise returned from [`PaymentRequest.show()`](../paymentrequest/show). In a real-world implementation this data would then be sent to a payment server.

    payment.show().then(paymentResponse => {
      var paymentData = {
        // payment method string
        method: paymentResponse.methodName,
        // payment details as you requested
        details: paymentResponse.details,
        // shipping address information
        address: toDict(paymentResponse.shippingAddress)
      };
      // Send information to the server
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/">Payment Request API</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`methodName`

60

15

No

Available only in nightly builds.

No

47

11.1

No

56

No

Available only in nightly builds.

43

11.3

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/methodName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/methodName</a>

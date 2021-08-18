PaymentResponse.details
=======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `details` read-only property of the [`PaymentResponse`](../paymentresponse) interface returns a JSON-serializable object that provides a payment method specific message used by the merchant to process the transaction and determine a successful funds transfer.

This data is returned by the payment app that satisfies the payment request, and must conform to the structure defined in the [`BasicCardResponse`](../basiccardresponse) dictionary.

Syntax
------

    var detailsObject = PaymentResponse.details;

Example
-------

The following example extracts the details from the [`PaymentResponse`](../paymentresponse) object to the promise returned from [`PaymentRequest.show()`](../paymentrequest/show). In a real-world implementation this data would then be sent to a payment server.

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

`details`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/details" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentResponse/details</a>

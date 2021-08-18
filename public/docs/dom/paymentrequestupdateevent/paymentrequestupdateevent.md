PaymentRequestUpdateEvent.PaymentRequestUpdateEvent()
=====================================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PaymentRequestUpdateEvent` constructor creates a new [`PaymentRequestUpdateEvent`](../paymentrequestupdateevent) object which enables a web page to update the details of a [`PaymentRequest`](../paymentrequest) in response to a user action. Actual updates are made by passing options to the [`updateWith()`](updatewith) method.

Syntax
------

    var paymentRequestUpdateEvent = new PaymentRequestUpdateEvent()

### Parameters

None.

### Return value

A new `PaymentRequestUpdateEvent` object.[Payment Request API  
<span class="small">The definition of 'PaymentRequestUpdateEvent' in that specification.</span>](https://w3c.github.io/payment-request/#paymentrequestupdateevent-interface)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#constructor-0">Payment Request API<br />
<span class="small">The definition of 'PaymentRequestUpdateEvent()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentRequestUpdateEvent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestUpdateEvent/PaymentRequestUpdateEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentRequestUpdateEvent/PaymentRequestUpdateEvent</a>

PaymentDetailsUpdate.error
==========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentDetailsUpdate`](../paymentdetailsupdate) dictionary's `error` property is a human-readable [`DOMString`](../domstring) which provides an error message to be displayed if the specified information doesn't offer any valid shipping options.

Syntax
------

    errorString = paymentDetailsUpdate.error;

    paymentDetailsUpdate.error = errorString;

### Value

A [`DOMString`](../domstring) specifying the string to display to the user if the information specified in the `PaymentDetailsUpdate` doesn't provide any valid shipping options. This happens if both of the following are true:

-   The [`PaymentRequest`](../paymentrequest) specifies using its <span class="page-not-created">`requestShipping`</span> property that shipping information is required.
-   The [`PaymentDetailsUpdate`](../paymentdetailsupdate) object specifies no valid shipping options in its <span class="page-not-created">`shippingOptions`</span> list.

This message can be used to explain to the user why they cannot submit their payment as currently specified—whether that's because the selected products cannot be shipped to their region or because their address is not served by any of the shipping companies you use.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentdetailsupdate-error">Payment Request API<br />
<span class="small">The definition of 'PaymentDetailsUpdate.error' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`error`

61

≤18

55

Available only in nightly builds.

No

No

?

No

60

55

Available only in nightly builds.

No

?

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentDetailsUpdate/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentDetailsUpdate/error</a>

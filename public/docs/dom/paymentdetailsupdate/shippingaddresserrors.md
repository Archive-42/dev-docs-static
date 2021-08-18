# PaymentDetailsUpdate.shippingAddressErrors

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentDetailsUpdate`](../paymentdetailsupdate) dictionary's `shippingAddressErrors` property, if present, contains an [`AddressErrors`](../addresserrors) object whose contents provide error messages for one or more of the values in the [`PaymentAddress`](../paymentaddress) specified as [`PaymentRequest.shippingAddress`](../paymentrequest/shippingaddress).

## Syntax

    var addressErrors = PaymentDetailsUpdate.shippingAddressErrors;

### Value

An [`AddressErrors`](../addresserrors) object, which contains [`DOMString`](../domstring)s describing errors in the properties of a [`PaymentAddress`](../paymentaddress). For each property in `PaymentAddress`, a property by the same name is found in `shippingAddressErrors` if and only if a validation error occurred for that property. In that case, the property in `shippingAddressErrors` is a string describing the validation error, ideally including suggestions about fixing the error.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentdetailsupdate-shippingaddresserrors">Payment Request API<br />
<span class="small">The definition of 'PaymentDetailsUpdate.shippingAddressErrors' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`shippingAddressErrors`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentDetailsUpdate/shippingAddressErrors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentDetailsUpdate/shippingAddressErrors</a>

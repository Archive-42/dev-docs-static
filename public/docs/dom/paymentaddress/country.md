PaymentAddress.country
======================

The `country` read-only property of the [`PaymentAddress`](../paymentaddress) interface is a string identifying the address's country using the [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) standard. The string is always in its canonical upper-case form.

Some examples of valid `country` values: `"US"`, `"GB"`, `"CN"`, or `"JP"`.

Syntax
------

    var paymentCountry = PaymentAddress.country;

### Value

A [`DOMString`](../domstring) which contains the ISO3166-1 alpha-2 code identifying the country in which the address is located, or an empty string if no country is available, which frequently can be assumed to mean "same country as the site owner."

Usage notes
-----------

If the payment handler validates the address and determines that the value of `country` is invalid, a call to [`PaymentRequestUpdateEvent.updateWith()`](../paymentrequestupdateevent/updatewith) will be made with a `details` object containing a [`shippingAddressErrors`](../paymentdetailsupdate/shippingaddresserrors) field. That field contains an [`AddressErrors`](../addresserrors)-compliant object whose [`country`](../addresserrors/country) property is a string indicating the validation error that occurred and, if possible, suggests how to fix it.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentaddress">Payment Request API<br />
<span class="small">The definition of 'PaymentAddress.country' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

BCD tables only load in the browser

-   [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
-   [`PaymentDetailsUpdate.shippingAddressErrors`](../paymentdetailsupdate/shippingaddresserrors)
-   [`AddressErrors.country`](../addresserrors/country)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/country" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/country</a>

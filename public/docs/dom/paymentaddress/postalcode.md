PaymentAddress.postalCode
=========================

The `postalCode` read-only property of the [`PaymentAddress`](../paymentaddress) interface returns a string containing a code used by a jurisdiction for mail routing, for example, the [ZIP Code](https://en.wikipedia.org/wiki/ZIP_Code) in the United States or the [Postal Index Number](https://en.wikipedia.org/wiki/Postal_Index_Number) (PIN code) in India.

Syntax
------

    var paymentPostalCode = PaymentAddress.postalCode;

### Value

A [`DOMString`](../domstring) which contains the postal code portion of the address. A postal code is a string (either numeric or alphanumeric) which is used by a postal service to optimize mail routing and delivery.

Various countries use different terms for this. In most of the world, it's known as the "post code" or "postal code." In the United States, the ZIP code is used. India uses PIN codes.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentaddress-postalcode">Payment Request API<br />
<span class="small">The definition of 'PaymentAddress.postalCode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

BCD tables only load in the browser

-   Universal Postal Union: [Post code lookup service](https://www.upu.int/en/resources/postcodes/looking-up-a-postcode.html)
-   Universal Postal Union: [Universal Post\*Code® Database](https://www.upu.int/en/resources/postcodes/universal-postcoder-database.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/postalCode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/postalCode</a>

# PaymentCurrencyAmount

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PaymentCurrencyAmount` dictionary describes an amount of money in terms of both a number of units and the currency (US dollars, Euro, yen, etc.), and is part of the [Payment Request API](payment_request_api). This is used to specify the prices of both line items on a payment, using [`PaymentItem`](paymentitem) objects, and to provide the cost of a shipping option, using <span class="page-not-created">`PaymentShippingOption`</span>.

## Properties

All properties are required.

[`currency`](paymentcurrencyamount/currency)  
A string containing a valid 3-letter [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency identifier ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) indicating the currency used for the payment `value`.

[`value`](paymentcurrencyamount/value)  
A string containing a valid decimal value representing the mount of currency constituting the payment amount. This string must only contain an optional leading "-" to indicate a negative value, then one or more digits from 0 to 9, and an optional decimal point (".", regardless of locale) followed by at least one more digit. No whitespace is permitted.

### Obsolete properties

_These properties have been removed from the specification and should no longer be used._

[`currencySystem`](paymentcurrencyamount/currencysystem) <span class="badge inline optional">Optional</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A string describing the standard or specification as well as the currency system identifier within that system which was used to provide the `value`. This has been removed; instead of allowing sites to choose the standard to use, ISO 4217 is always used for the `currency` identifier now.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentcurrencyamount">Payment Request API<br />
<span class="small">The definition of 'PaymentCurrencyAmount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PaymentCurrencyAmount`

56

≤79

55

Available only in nightly builds.

No

No

?

56

56

55

Available only in nightly builds.

No

?

6.0

`currency`

56

≤79

63

Available only in nightly builds.

No

No

?

56

56

63

Available only in nightly builds.

No

?

6.0

`currencySystem`

No

No

55-64

Removed from the specification; currencies are now always identified using ISO 4217. This was only available in nightly builds.

No

No

?

No

No

55-64

Removed from the specification; currencies are now always identified using ISO 4217. This was only available in nightly builds.

No

?

No

`value`

56

≤79

63

Available only in nightly builds.

No

No

?

56

56

63

Available only in nightly builds.

No

?

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentCurrencyAmount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentCurrencyAmount</a>

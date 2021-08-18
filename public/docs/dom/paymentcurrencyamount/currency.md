# PaymentCurrencyAmount.currency

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentCurrencyAmount`](../paymentcurrencyamount) property `currency` is a string which specifies the currency in which the [`value`](value) is specified. The value is always specified using the 3-letter codes defined by the [ISO 4127](https://www.iso.org/iso-4217-currency-codes.html) standard.

## Syntax

    currency = paymentCurrencyAmount.currency;

### Value

A [`DOMString`](../domstring) specifying the canonical, three-character currency identification code defined by the [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard. This is the currency in which the payment's [`value`](value) is given. All currency values must include the currency system in this property.

## Example

This example represents the price of $42.95 in US dollars.

    let itemPrice = {
      currency: "USD",
      value: "42.95"
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentcurrencyamount-currency">Payment Request API<br />
<span class="small">The definition of 'PaymentCurrencyAmount.currency' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

## See also

- [Payment Request API](../payment_request_api)
- [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
- [Payment processing concepts](../payment_request_api/concepts)
- [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) on Wikipedia

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentCurrencyAmount/currency" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentCurrencyAmount/currency</a>

# PaymentCurrencyAmount.value

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The [`PaymentCurrencyAmount`](../paymentcurrencyamount) property `value` is a string containing the decimal numeric value of the payment, specified in the currency units indicated by the [`currency`](currency) property. The contents of this string must be a valid decimal number; that is, some number of digits between 0 and 9 with up to one optional decimal point. An optional leading minus sign ("-") can be included to indicate a negative value, such as to represent a refund or discount.

**Important note:** The number given in this string is always specified using the period (".") as the decimal point, rather than the comma (","), even if the user's locale normally uses the comma. You must convert the entered text to this form or it will not be valid.

## Syntax

    value = paymentCurrencyAmount.value;

### Value

A [`DOMString`](../domstring) indicating the numeric value of the payment. This must be a valid decimal number, with an optional leading minus sign ("-"), then one or more decimal digits 0 through 9, optionally with a decimal point (".") with at least one digit following it to represent fractional units. There must not be any leading or trailing whitespace in the string.

For uniformity and consistency, the value is always given using the period (".") as the decimal character, regardless of the user's locale. You need to convert the value to this format before submitting the payment.

See the example [Verifying a properly formatted price](#verifying_a_properly_formatted_price) below for a simple regular expression that can be used to validate the `value` string prior to submission.

## Examples

### Representing prices

This example represents the price of $42.95 in US dollars:

    let itemPrice = {
      currency: "USD",
      value: "42.95"
    };

This example specifies a price of £7.77:

    let shippingCost = {
      currency: "GBP",
      value: "7.77"
    }

This example specifies a price of 1000¥:

    let price = {
      currency: "JPY",
      value: "1000"
    }

### Verifying a properly formatted price

You can ensure that the value entered as a price is formatted correctly prior to submission by matching it against a simple [regular expression](https://developer.mozilla.org/en-US/docs/Glossary/Regular_expression):

    function checkPriceFormat(price) {
      let validRegex = /^-?[0-9]+(\.[0-9]+)?$/;

      return validRegex.test(price);
    }

This function, `checkPriceFormat()`, will return `true` if the specified price string is formatted properly, or `false` if it's not.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentcurrencyamount-value">Payment Request API<br />
<span class="small">The definition of 'PaymentCurrencyAmount.value' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

## See also

- [Payment Request API](../payment_request_api)
- [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
- [Payment processing concepts](../payment_request_api/concepts)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentCurrencyAmount/value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentCurrencyAmount/value</a>

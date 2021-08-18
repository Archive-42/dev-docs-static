PaymentCurrencyAmount.currencySystem
====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning**

This property has been removed from the specification and should no longer be used; the currency is now *always* specified using ISO 4127.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The *obsolete* [`PaymentCurrencyAmount`](../paymentcurrencyamount) property `currencySystem` is a string which specifies the standard being used to specify the [`currency`](currency) the [`value`](value) is specified in. For example, the default is `urn:iso:std:iso:4217`, which specifies that the standard used is [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217).

Syntax
------

    currencySystem = paymentCurrencyAmount.currencySystem;

### Value

A [`DOMString`](../domstring) which specifies the currency standard used to specify the [`currency`](currency) in which the payment value is represented. The default, `urn:iso:std:iso:4217`, indicates the [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard.

This obsolete property was removed in the [May 3, 2018 update](https://www.w3.org/TR/2018/CR-payment-request-20180503) of the Payment Request API specification.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentcurrencyamount">Payment Request API<br />
<span class="small">The definition of 'PaymentCurrencyAmount' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No longer part of the specification</td></tr><tr class="even"><td><a href="https://w3c.github.io/payment-request/#dom-paymentcurrencyamount">Payment Request API</a><br />
<span class="small"><a href="https://www.w3.org/TR/2018/CR-payment-request-20180320/#dom-paymentcurrencyamount-currencysystem">The definition of 'PaymentCurrencyAmount.currencySystem' in that specification.</a></span></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The March 20, 2018 version of the specification; the last one to include this property</td></tr></tbody></table>

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

See also
--------

-   [Payment Request API](../payment_request_api)
-   [Using the Payment Request API](../payment_request_api/using_the_payment_request_api)
-   [Payment processing concepts](../payment_request_api/concepts)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentCurrencyAmount/currencySystem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentCurrencyAmount/currencySystem</a>

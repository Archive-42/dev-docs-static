# PaymentAddress.region

The read-only `region` property of the [`PaymentAddress`](../paymentaddress) interface returns a string containing the top-level administrative subdivision of the country in which the address is located. For example, this may be a state, province, oblast, or prefecture.

## Syntax

    var paymentRegion = PaymentAddress.region;

### Value

A [`DOMString`](../domstring) specifying the top-level administrative subdivision within the country in which the address is located. This region has different names in different countries, such as: state, province, oblast, prefecture, or county.

## Usage notes

In some countries, like Belgium, it's uncommon for people to provide a region as part of their postal address. In such cases, the browser returns an empty string as the value of `region`. However, the address should still be acceptable to use for its intended purpose (e.g., to ship a product). However, always verify addresses to make sure what the user provides is usable.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentaddress-region">Payment Request API<br />
<span class="small">The definition of 'PaymentAddress.region' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`region`

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

44

11.3

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/region" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/region</a>

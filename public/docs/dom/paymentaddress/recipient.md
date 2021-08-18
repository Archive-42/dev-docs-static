PaymentAddress.recipient
========================

The read-only `recipient` property of the [`PaymentAddress`](../paymentaddress) interface returns a string containing the name of the recipient, purchaser, or contact person at the payment address.

Syntax
------

    var paymentRecipient = PaymentAddress.recipient;

### Value

A [`DOMString`](../domstring) giving the name of the person receiving or paying for the purchase, or the name of a contact person in other contexts. If no name is available, this string is empty.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentaddress-recipient">Payment Request API<br />
<span class="small">The definition of 'PaymentAddress.recipient' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`recipient`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/recipient" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/recipient</a>

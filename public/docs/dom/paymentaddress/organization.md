# PaymentAddress.organization

The `organization` read-only property of the [`PaymentAddress`](../paymentaddress) interface returns a string containing the name of the organization, firm, company, or institution at the address.

## Syntax

    var paymentOrganization = PaymentAddress.organization;

### Value

A [`DOMString`](../domstring) whose value is the name of the organization or company located at the address described by the `PaymentAddress` object. This should be the name of the organization that is to receive the shipment for shipping addresses, or which is repsonsible for payment for payment addresses.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentaddress-organization">Payment Request API<br />
<span class="small">The definition of 'PaymentAddress.organization' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`organization`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/organization" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/organization</a>

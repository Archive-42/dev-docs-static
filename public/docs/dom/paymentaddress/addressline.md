PaymentAddress.addressLine
==========================

The `addressLine` read-only property of the [`PaymentAddress`](../paymentaddress) interface is an array of [`DOMString`](../domstring) objects, each specifying a line of the address that is not covered by one of the other properties of `PaymentAddress`. These lines may include the street name, house number, apartment number, rural delivery route, descriptive instructions, or post office box.

Syntax
------

    var paymentAddressLines = PaymentAddress.addressLine;

### Value

An array of [`DOMString`](../domstring) objects, each containing one line of the address. For example, the `addressLine` array for the Mozilla Space in London would have the following entries:

<table><caption>Example showing <code>addressLine</code> entries for an address in London </caption><thead><tr class="header"><th>Index</th><th>addressLine[] value</th></tr></thead><tbody><tr class="odd"><td>0</td><td>Metal Box Factory</td></tr><tr class="even"><td>1</td><td>Suite 441, 4th floor</td></tr><tr class="odd"><td>2</td><td>30 Great Guildford Street</td></tr></tbody></table>

These, combined with additional values for other properties of the [`PaymentAddress`](../paymentaddress), would represent the full address, which is:

Mozilla  
Metal Box Factory  
Suite 441, 4th floor  
30 Great Guildford Street  
London SE1 0HS  
United Kingdom

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-paymentaddress-addressline">Payment Request API<br />
<span class="small">The definition of 'PaymentAddress.addressLine' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`addressLine`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/addressLine" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/addressLine</a>

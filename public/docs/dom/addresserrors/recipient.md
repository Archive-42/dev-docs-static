# AddressErrors.recipient

An object based on [`AddressErrors`](../addresserrors) includes a `recipient` property when the address's [`recipient`](../paymentaddress/recipient) property couldn't be validated. The returned string explains the error and should offer suggestions for how to correct it.

## Syntax

    var recipientError = AddressErrors.recipient;

### Value

If the value specified in the [`PaymentAddress`](../paymentaddress) object's [`recipient`](../paymentaddress/recipient) property could not be validated, this property contains a [`DOMString`](../domstring) offering a human-readable explanation of the validation error and offers suggestions for correcting it.

If the `recipient` value was validated successfully, this property is not included in the `AddressErrors` object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-addresserrors-recipient">Payment Request API<br />
<span class="small">The definition of 'AddressErrors.recipient' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AddressErrors.recipient`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/recipient" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/recipient</a>

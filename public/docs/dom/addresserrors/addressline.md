# AddressErrors.addressLine

An object based on [`AddressErrors`](../addresserrors) includes an `addressLine` property when validation of the address finds one or more errors in the array of strings in the address's [`addressLine`](../paymentaddress/addressline). The returned string explains the error and should offer suggestions for how to correct it.

## Syntax

    var addressLineError = AddressErrors.addressLine;

### Value

If an error occurred during validation of the address due to one of the strings in the [`addressLine`](../paymentaddress/addressline) array having an invalid value, this property is set to a [`DOMString`](../domstring) providing a human-readable error message explaining the validation error.

The text should also include, when possible, advice about how to go about correcting the error.

If the [`PaymentAddress`](../paymentaddress) object's `addressLine` property was determined to be valid, this property is not included in the `AddressErrors` dictionary.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-addresserrors-addressline">Payment Request API<br />
<span class="small">The definition of 'AddressErrors.addressLine' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AddressErrors.addressLine`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/addressLine" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/addressLine</a>

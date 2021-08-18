# AddressErrors.country

An object based on [`AddressErrors`](../addresserrors) includes a `country` property if during validation of the address the specified value of [`country`](../paymentaddress/country) was determined to be invalid. The value is a string describing the error and should offer suggestions for how to correct it.

## Syntax

    var countryError = AddressErrors.country;

### Value

If an error occurred during validation of the address due to the [`country`](../paymentaddress/country) property having an invalid value, this property is set to a [`DOMString`](../domstring) providing a human-readable error message explaining the validation error.

The text should also include, when possible, advice about how to go about correcting the error.

If the [`PaymentAddress`](../paymentaddress) object's `country` property was determined to be valid, this property is not included in the dictionary.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-addresserrors-country">Payment Request API<br />
<span class="small">The definition of 'AddressErrors.country' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AddressErrors.country`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/country" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/country</a>

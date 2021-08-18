# AddressErrors.regionCode

An object based on [`AddressErrors`](../addresserrors) includes a `regionCode` property when the address's [`regionCode`](../paymentaddress/regioncode) property couldn't be validated. The returned string explains the error and should offer suggestions for how to correct it.

## Syntax

    var regionCodeError = AddressErrors.regionCode;

### Value

If the value specified in the [`PaymentAddress`](../paymentaddress) object's [`regionCode`](../paymentaddress/regioncode) property could not be validated, this property contains a [`DOMString`](../domstring) offering a human-readable explanation of the validation error and offers suggestions for correcting it.

If the `regionCode` value was validated successfully, this property is not included in the `AddressErrors` object.

## Usage notes

The region code is derived from the ISO 3166-2 country subdivision name standard.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-addresserrors-regioncode">Payment Request API<br />
<span class="small">The definition of 'AddressErrors.regionCode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AddressErrors.regionCode`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [United Nations: UN/LOCODE Country Subdivisions ISO 3166-2](https://www.unece.org/cefact/locode/subdivisions.html)
- [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) on Wikipedia

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/regionCode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/regionCode</a>

# AddressErrors.dependentLocality

An object based on [`AddressErrors`](../addresserrors) includes a `dependentLocality` property when the address's [`dependentLocality`](../paymentaddress/dependentlocality) property couldn't be validated. The returned string explains the error and should offer suggestions for how to correct it.

## Syntax

    var localityError = AddressErrors.dependentLocality;

### Value

If the value specified in the [`PaymentAddress`](../paymentaddress) object's [`dependentLocality`](../paymentaddress/dependentlocality) property could not be validated, this property contains a [`DOMString`](../domstring) offering a human-readable explanation of the validation error and offers suggestions for correcting it.

If the `dependentLocality` value was validated successfully, this property is not included in the `AddressErrors` object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-addresserrors-dependentlocality">Payment Request API<br />
<span class="small">The definition of 'AddressErrors.dependentLocality' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AddressErrors.dependentLocality`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/dependentLocality" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/dependentLocality</a>

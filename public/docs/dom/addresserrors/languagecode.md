# AddressErrors.languageCode

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

An object based on [`AddressErrors`](../addresserrors) includes a `languageCode` property when the address's [`languageCode`](../paymentaddress/languagecode) property couldn't be validated. The returned string explains the error and should offer suggestions for how to correct it.

## Syntax

    var languageError = AddressErrors.languageCode;

### Value

If the value specified in the [`PaymentAddress`](../paymentaddress) object's [`languageCode`](../paymentaddress/languagecode) property could not be validated, this property contains a [`DOMString`](../domstring) offering a human-readable explanation of the validation error and offers suggestions for correcting it.

This validation might be as simple as ensuring the text of the string is compliant with the syntax defined in [BCP-47](https://datatracker.ietf.org/doc/html/bcp47), or as detailed as actually verifying that the specified string matches a value from a database.

If the `languageCode` value was validated successfully, this property is not included in the `AddressErrors` object.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/payment-request/#dom-addresserrors-languagecode">Payment Request API<br />
<span class="small">The definition of 'AddressErrors.languageCode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.AddressErrors.languageCode`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/languageCode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AddressErrors/languageCode</a>

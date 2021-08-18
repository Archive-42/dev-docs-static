# EcKeyGenParams

The `EcKeyGenParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey), when generating any elliptic-curve-based key pair: that is, when the algorithm is identified as either of [ECDSA](subtlecrypto/sign#ecdsa) or [ECDH](subtlecrypto/derivekey#ecdh).

## Properties

`name`  
A [`DOMString`](domstring). This should be set to `ECDSA` or `ECDH`, depending on the algorithm you want to use.

`namedCurve`  
A [`DOMString`](domstring) representing the name of the elliptic curve to use. This may be any of the following names for [NIST](https://www.nist.gov/)-approved curves:

- `P-256`
- `P-384`
- `P-521`

## Examples

See the examples for [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-EcKeyGenParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.EcKeyGenParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EcKeyGenParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EcKeyGenParams</a>

# RsaHashedImportParams

The `RsaHashedImportParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.importKey()`](subtlecrypto/importkey) or [`SubtleCrypto.unwrapKey()`](subtlecrypto/unwrapkey), when importing any RSA-based key pair: that is, when the algorithm is identified as any of [RSASSA-PKCS1-v1_5](subtlecrypto/sign#rsassa-pkcs1-v1_5), [RSA-PSS](subtlecrypto/sign#rsa-pss), or [RSA-OAEP](subtlecrypto/encrypt#rsa-oaep).

## Properties

`name`  
A [`DOMString`](domstring). This should be set to `RSASSA-PKCS1-v1_5`, `RSA-PSS`, or `RSA-OAEP`, depending on the algorithm you want to use.

`hash`  
A [`DOMString`](domstring) representing the name of the [digest function](subtlecrypto#digest_algorithms) to use. This can be one of `SHA-256`, `SHA-384`, or `SHA-512`.

**Warning**: Although you can technically pass `SHA-1` here, this is strongly discouraged as it is considered vulnerable.

## Examples

See the examples for [`SubtleCrypto.importKey()`](subtlecrypto/importkey).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-RsaHashedImportParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.RsaHashedImportParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- [`SubtleCrypto.importKey()`](subtlecrypto/importkey).
- [`SubtleCrypto.unwrapKey()`](subtlecrypto/unwrapkey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RsaHashedImportParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RsaHashedImportParams</a>

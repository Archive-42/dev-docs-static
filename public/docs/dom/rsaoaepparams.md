# RsaOaepParams

The `RsaOaepParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.encrypt()`](subtlecrypto/encrypt), [`SubtleCrypto.decrypt()`](subtlecrypto/decrypt), [`SubtleCrypto.wrapKey()`](subtlecrypto/wrapkey), or [`SubtleCrypto.unwrapKey()`](subtlecrypto/unwrapkey), when using the [RSA_OAEP](subtlecrypto/encrypt#rsa-oaep) algorithm.

## Properties

`name`  
A [`DOMString`](domstring). This should be set to `RSA-OAEP`.

`label` <span class="badge inline optional">Optional</span>  
A [`BufferSource`](buffersource) — an array of bytes that does not itself need to be encrypted but which should be bound to the ciphertext. A digest of the label is part of the input to the encryption operation.

Unless your application calls for a label, you can just omit this argument and it will not affect the security of the encryption operation.

## Examples

See the examples for [`SubtleCrypto.encrypt()`](subtlecrypto/encrypt) and [`SubtleCrypto.decrypt()`](subtlecrypto/decrypt).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-RsaOaepParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.RsaOaepParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- [`SubtleCrypto.encrypt()`](subtlecrypto/encrypt).
- [`SubtleCrypto.decrypt()`](subtlecrypto/decrypt).
- [`SubtleCrypto.wrapKey()`](subtlecrypto/wrapkey).
- [`SubtleCrypto.unwrapKey()`](subtlecrypto/unwrapkey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RsaOaepParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RsaOaepParams</a>

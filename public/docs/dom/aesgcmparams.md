# AesGcmParams

The `AesGcmParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.encrypt()`](subtlecrypto/encrypt), [`SubtleCrypto.decrypt()`](subtlecrypto/decrypt), [`SubtleCrypto.wrapKey()`](subtlecrypto/wrapkey), or [`SubtleCrypto.unwrapKey()`](subtlecrypto/unwrapkey), when using the [AES-GCM](subtlecrypto/encrypt#aes-gcm) algorithm.

For details of how to supply appropriate values for this parameter, see the specification for AES-GCM: [NIST SP800-38D](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-38d.pdf), in particular section 5.2.1.1 on Input Data.

## Properties

`name`  
A [`DOMString`](domstring). This should be set to `AES-GCM`.

`iv`  
A [`BufferSource`](buffersource) — the initialization vector. This must be unique for every encryption operation carried out with a given key. Put another way: never reuse an IV with the same key. The AES-GCM specification recommends that the IV should be 96 bits long, and typically contains bits from a random number generator. [Section 8.2 of the specification](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-38d.pdf#%5B%7B%22num%22%3A65%2C%22gen%22%3A0%7D%2C%7B%22name%22%3A%22XYZ%22%7D%2C0%2C792%2Cnull%5D) outlines methods for constructing IVs. Note that the IV does not have to be secret, just unique: so it is OK, for example, to transmit it in the clear alongside the encrypted message.

`additionalData` <span class="badge inline optional">Optional</span>  
A [`BufferSource`](buffersource). This contains additional data that will not be encrypted but will be authenticated along with the encrypted data. If `additionalData` is given here then the same data must be given in the corresponding call to `decrypt()`: if the data given to the `decrypt()` call does not match the original data, the decryption will throw an exception. This gives you a way to authenticate associated data without having to encrypt it.

The bit length of `additionalData` must be `≤ 264-1`.

The `additionalData` property is optional and may be omitted without compromising the security of the encryption operation.

`tagLength` <span class="badge inline optional">Optional</span>  
A `Number`. This determines the size in bits of the authentication tag generated in the encryption operation and used for authentication in the corresponding decryption.

According to the [Web Crypto specification](https://www.w3.org/TR/WebCryptoAPI/#dfn-AesGcmParams) this must have one of the following values: 32, 64, 96, 104, 112, 120, or 128. The AES-GCM specification recommends that it should be 96, 104, 112, 120 or 128, although 32 or 64 bits may be acceptable in some applications: [Appendix C of the specification](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-38d.pdf#%5B%7B%22num%22%3A92%2C%22gen%22%3A0%7D%2C%7B%22name%22%3A%22XYZ%22%7D%2C0%2C792%2Cnull%5D) provides additional guidance here.

`tagLength` is optional and defaults to 128 if it is not specified.

## Examples

See the examples for [`SubtleCrypto.encrypt()`](subtlecrypto/encrypt) and [`SubtleCrypto.decrypt()`](subtlecrypto/decrypt).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-AesGcmParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.AesGcmParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- [`SubtleCrypto.encrypt()`](subtlecrypto/encrypt).
- [`SubtleCrypto.decrypt()`](subtlecrypto/decrypt).
- [`SubtleCrypto.wrapKey()`](subtlecrypto/wrapkey).
- [`SubtleCrypto.unwrapKey()`](subtlecrypto/unwrapkey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AesGcmParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AesGcmParams</a>

# AesCbcParams

The `AesCbcParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.encrypt()`](subtlecrypto/encrypt), [`SubtleCrypto.decrypt()`](subtlecrypto/decrypt), [`SubtleCrypto.wrapKey()`](subtlecrypto/wrapkey), or [`SubtleCrypto.unwrapKey()`](subtlecrypto/unwrapkey), when using the [AES-CBC](subtlecrypto/encrypt#aes-cbc) algorithm.

## Properties

`name`  
A [`DOMString`](domstring). This should be set to `AES-CBC`.

`iv`  
A [`BufferSource`](buffersource). The initialization vector. Must be 16 bytes, unpredictable, and preferably cryptographically random. However, it need not be secret (for example, it may be transmitted unencrypted along with the ciphertext).

## Examples

See the examples for [`SubtleCrypto.encrypt()`](subtlecrypto/encrypt) and [`SubtleCrypto.decrypt()`](subtlecrypto/decrypt).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-AesCbcParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.AesCbcParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- CBC mode is defined in section 6.2 of the [NIST SP800-38A standard](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-38a.pdf#%5B%7B%22num%22%3A70%2C%22gen%22%3A0%7D%2C%7B%22name%22%3A%22Fit%22%7D%5D).
- [`SubtleCrypto.encrypt()`](subtlecrypto/encrypt).
- [`SubtleCrypto.decrypt()`](subtlecrypto/decrypt).
- [`SubtleCrypto.wrapKey()`](subtlecrypto/wrapkey).
- [`SubtleCrypto.unwrapKey()`](subtlecrypto/unwrapkey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AesCbcParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AesCbcParams</a>

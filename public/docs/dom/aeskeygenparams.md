# AesKeyGenParams

The `AesKeyGenParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey), when generating an AES key: that is, when the algorithm is identified as any of [AES-CBC](subtlecrypto/encrypt#aes-cbc), [AES-CTR](subtlecrypto/encrypt#aes-ctr), [AES-GCM](subtlecrypto/encrypt#aes-gcm), or [AES-KW](subtlecrypto/wrapkey#aes-kw).

## Properties

`name`  
A [`DOMString`](domstring). This should be set to `AES-CBC`, `AES-CTR`, `AES-GCM`, or `AES-KW`, depending on the algorithm you want to use.

`length`  
A `Number` — the length in bits of the key to generate. This must be one of: 128, 192, or 256.

## Examples

See the examples for [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-AesKeyGenParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.AesKeyGenParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AesKeyGenParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AesKeyGenParams</a>

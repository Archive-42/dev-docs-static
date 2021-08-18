# RsaPssParams

The `RsaPssParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.sign()`](subtlecrypto/sign) or [`SubtleCrypto.verify()`](subtlecrypto/verify), when using the [RSA-PSS](subtlecrypto/sign#rsa-pss) algorithm.

## Properties

`name`  
A [`DOMString`](domstring). This should be set to `RSA-PSS`.

`saltLength`  
A `long` integer representing the length of the random salt to use, in bytes.

[RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447) says that "Typical salt lengths" are either 0 or the length of the output of the [digest algorithm](subtlecrypto#digest_algorithms) that was selected when this key was [generated](subtlecrypto/generatekey). For example, if you use [SHA-256](subtlecrypto#sha-256) as the digest algorithm, this could be 32.

The maximum size of `saltLength` is given by:

    Math.ceil((keySizeInBits - 1)/8) - digestSizeInBytes - 2

So for a key length of 2048 bits and a digest output size of 32 bytes, the maximum size would be 222.

## Examples

See the examples for [`SubtleCrypto.sign()`](subtlecrypto/sign) and [`SubtleCrypto.verify()`](subtlecrypto/verify).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-RsaPssParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.RsaPssParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- [RFC 3447: RSASSA-PSS](https://datatracker.ietf.org/doc/html/rfc3447#section-8.1)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RsaPssParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RsaPssParams</a>

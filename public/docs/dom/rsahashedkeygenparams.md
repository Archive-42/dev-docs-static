# RsaHashedKeyGenParams

The `RsaHashedKeyGenParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey), when generating any RSA-based key pair: that is, when the algorithm is identified as any of [RSASSA-PKCS1-v1_5](subtlecrypto/sign#rsassa-pkcs1-v1_5), [RSA-PSS](subtlecrypto/sign#rsa-pss), or [RSA-OAEP](subtlecrypto/encrypt#rsa-oaep).

## Properties

`name`  
A [`DOMString`](domstring). This should be set to `RSASSA-PKCS1-v1_5`, `RSA-PSS`, or `RSA-OAEP`, depending on the algorithm you want to use.

`modulusLength`  
A `Number`. The length in bits of the RSA modulus. This should be at least 2048: see for example see [NIST SP 800-131A Rev. 1](https://csrc.nist.gov/publications/detail/sp/800-131a/rev-1/final). Some organizations are now recommending that it should be 4096.

`publicExponent`  
A [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array). The public exponent. Unless you have a good reason to use something else, specify 65537 here (`[0x01, 0x00, 0x01]`).

`hash`  
A [`DOMString`](domstring) representing the name of the [digest function](subtlecrypto/digest) to use. You can pass any of `SHA-256`, `SHA-384`, or `SHA-512` here.

**Warning**: Although you can technically pass `SHA-1` as a value here, this is strongly discouraged as SHA-1 is considered vulnerable.

## Examples

See the examples for [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-RsaHashedKeyGenParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.RsaHashedKeyGenParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RsaHashedKeyGenParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RsaHashedKeyGenParams</a>

# CryptoKey

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `CryptoKey` interface of the [Web Crypto API](web_crypto_api) represents a cryptographic [key](https://developer.mozilla.org/en-US/docs/Glossary/Key) obtained from one of the [`SubtleCrypto`](subtlecrypto) methods [`generateKey()`](subtlecrypto/generatekey), [`deriveKey()`](subtlecrypto/derivekey), [`importKey()`](subtlecrypto/importkey), or [`unwrapKey()`](subtlecrypto/unwrapkey).

For security reasons, the `CryptoKey` interface can only be used in a [secure context](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts).

## Properties

`CryptoKey.type`  
String which may take one of the following values:

- `"secret"`: This key is a secret key for use with a [symmetric algorithm](https://developer.mozilla.org/en-US/docs/Glossary/Symmetric-key_cryptography).
- `"private"`: This key is the private half of an [asymmetric algorithm's](https://developer.mozilla.org/en-US/docs/Glossary/Public-key_cryptography) `CryptoKeyPair`.
- `"public"`: This key is the public half of an [asymmetric algorithm's](https://developer.mozilla.org/en-US/docs/Glossary/Public-key_cryptography) `CryptoKeyPair`.

`CryptoKey.extractable`  
[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the key may be extracted using [`SubtleCrypto.exportKey()`](subtlecrypto/exportkey) or [`SubtleCrypto.wrapKey()`](subtlecrypto/wrapkey).

- `true`: The key may be extracted.
- `false` The key may not be extracted. [`exportKey()`](subtlecrypto/exportkey) or [`wrapKey()`](subtlecrypto/wrapkey) will throw an exception if used to extract this key.

`CryptoKey.algorithm`  
An object describing the algorithm for which this key can be used and any associated extra parameters.

- `AesKeyGenParams` if the algorithm is any of the AES variants.
- `RsaHashedKeyGenParams` if the algorithm is any of the RSA variants.
- `EcKeyGenParams` if the algorithm is any of the EC variants.
- `HmacKeyGenParams` if the algorithm is HMAC.

`CryptoKey.usages`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of strings, indicating what can be done with the key. Possible values for array elements are:

- `"encrypt"`: The key may be used to [`encrypt`](subtlecrypto/encrypt) messages.
- `"decrypt"`: The key may be used to [`decrypt`](subtlecrypto/decrypt) messages.
- `"sign"`: The key may be used to [`sign`](subtlecrypto/sign) messages.
- `"verify"`: The key may be used to [`verify`](subtlecrypto/verify) signatures.
- `"deriveKey"`: The key may be used in [`deriving a new key`](subtlecrypto/derivekey).
- `"deriveBits"`: The key may be used in [`deriving bits`](subtlecrypto/derivebits).
- `"wrapKey"`: The key may be used to [`wrap a key`](subtlecrypto/wrapkey).
- `"unwrapKey"`: The key may be used to [`unwrap a key`](subtlecrypto/unwrapkey).

## Examples

The examples for `SubtleCrypto` methods often use `CryptoKey` objects. For example:

- `SubtleCrypto.generateKey()`
- `SubtleCrypto.deriveKey()`
- `SubtleCrypto.importKey()`
- `SubtleCrypto.exportKey()`
- `SubtleCrypto.wrapKey()`
- `SubtleCrypto.unwrapKey()`
- `SubtleCrypto.encrypt()`
- `SubtleCrypto.decrypt()`
- `SubtleCrypto.sign()`
- `SubtleCrypto.verify()`

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-CryptoKey">Web Cryptography API<br />
<span class="small">The definition of 'CryptoKey' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`CryptoKey`

37

12

34

No

24

No

37

37

34

24

No

3.0

`algorithm`

37

12

34

No

24

No

37

37

34

24

No

3.0

`extractable`

37

12

34

No

24

No

37

37

34

24

No

3.0

`secure_context_required`

60

79

75

No

47

No

60

60

No

47

No

8.0

`type`

37

12

34

No

24

No

37

37

34

24

No

3.0

`usages`

37

12

34

No

24

No

37

37

34

24

No

3.0

## See also

- [Web Crypto API](web_crypto_api)
- [Web security](https://developer.mozilla.org/en-US/docs/Web/Security)
- [Privacy, permissions, and incormation security](https://developer.mozilla.org/en-US/docs/Web/Privacy)
- [`Crypto`](crypto) and [`Crypto.subtle`](crypto/subtle).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CryptoKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CryptoKey</a>

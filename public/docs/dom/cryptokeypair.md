# CryptoKeyPair

The `CryptoKeyPair` dictionary of the [Web Crypto API](web_crypto_api) represents a key pair for an asymmetric cryptography algorithm, also known as a public-key algorithm.

A `CryptoKeyPair` object can be obtained using [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey), when the selected algorithm is one of the asymmetric algorithms: RSASSA-PKCS1-v1_5, RSA-PSS, RSA-OAEP, ECDSA, or ECDH.

It contains two properties, which are both `CryptoKey` objects: a `privateKey` property containing the private key and a `publicKey` property containing the public key.

## Properties

`CryptoKeyPair.privateKey`  
A `CryptoKey` object representing the private key. For encryption and decryption algorithms, this key is used to decrypt. For signing and verification algorithms it is used to sign.

`CryptoKeyPair.publicKey`  
A `CryptoKey` object representing the public key. For encryption and decryption algorithms, this key is used to encrypt. For signing and verification algorithms it is used to verify signatures.

## Examples

The examples for `SubtleCrypto` methods often use `CryptoKeyPair` objects. For example:

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-CryptoKeyPair">Web Cryptography API<br />
<span class="small">The definition of 'CryptoKeyPair' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CryptoKeyPair`

37

≤18

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

- [`SubtleCrypto.generateKey`](subtlecrypto/generatekey).
- [`SubtleCrypto.sign`](subtlecrypto/sign) and [`SubtleCrypto.verify`](subtlecrypto/verify).
- [`SubtleCrypto.encrypt`](subtlecrypto/encrypt) and [`SubtleCrypto.decrypt`](subtlecrypto/decrypt).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CryptoKeyPair" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CryptoKeyPair</a>

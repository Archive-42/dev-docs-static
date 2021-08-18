# Crypto

The `Crypto` interface represents basic cryptography features available in the current context. It allows access to a cryptographically strong random number generator and to cryptographic primitives.

**Note:** This feature is available in [Web Workers](web_workers_api).

The [Web Crypto API](web_crypto_api) is accessed through the [`Window.crypto`](window/crypto) property, which is a `Crypto` object.

## Properties

_This interface implements properties defined on [`RandomSource`](crypto/getrandomvalues)._

[`Crypto.subtle`](crypto/subtle) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>  
Returns a [`SubtleCrypto`](subtlecrypto) object providing access to common cryptographic primitives, like hashing, signing, encryption, or decryption.

## Methods

_This interface implements methods defined on [`RandomSource`](crypto/getrandomvalues)._

[`Crypto.getRandomValues()`](crypto/getrandomvalues)  
Fills the passed [`TypedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray) with cryptographically sound random values.

## Usage notes

You should avoid using the Web Crypto API on insecure contexts, even though the `Crypto` interface is present on insecure contexts, as is the [`Window.crypto`](window/crypto) property. In addition, the `Crypto` method [`getRandomValues()`](crypto/getrandomvalues) is available on insecure contexts, but the [`subtle`](crypto/subtle) property is not.

In general, you probably should just treat `Crypto` as available only on secure contexts.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#crypto-interface">Web Cryptography API<br />
<span class="small">The definition of 'Crypto' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Crypto`

11

12

26

11

15

6.1

≤37

18

26

14

6.1

1.0

`getRandomValues`

11

12

26

11

15

6.1

≤37

18

26

14

6.1

1.0

`subtle`

37

12

34

11

24

10.1

7

37

37

34

24

10.3

7

3.0

## See also

- [Web security](https://developer.mozilla.org/en-US/docs/Web/Security)
- [Secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts)
- [Features restricted to secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts/features_restricted_to_secure_contexts)
- [Transport Layer Security](https://developer.mozilla.org/en-US/docs/Web/Security/Transport_Layer_Security)
- [Strict-Transport-Security](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Crypto" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Crypto</a>

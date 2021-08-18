SubtleCrypto.generateKey()
==========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

Use the `generateKey()` method of the [`SubtleCrypto`](../subtlecrypto) interface to generate a new key (for symmetric algorithms) or key pair (for public-key algorithms).

Syntax
------

    const result = crypto.subtle.generateKey(algorithm, extractable, keyUsages);

### Parameters

-   *`algorithm`* is a dictionary object defining the type of key to generate and providing extra algorithm-specific parameters.
    -   For [RSASSA-PKCS1-v1\_5](sign#rsassa-pkcs1-v1_5), [RSA-PSS](sign#rsa-pss), or [RSA-OAEP](encrypt#rsa-oaep): pass an `RsaHashedKeyGenParams` object.
    -   For [ECDSA](sign#ecdsa) or [ECDH](derivekey#ecdh): pass an `EcKeyGenParams` object.
    -   For [HMAC](sign#hmac): pass an `HmacKeyGenParams` object.
    -   For [AES-CTR](encrypt#aes-ctr), [AES-CBC](encrypt#aes-cbc), [AES-GCM](encrypt#aes-gcm), or [AES-KW](encrypt#aes-kw): pass an `AesKeyGenParams` object.
-   `extractable` is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether it will be possible to export the key using [`SubtleCrypto.exportKey()`](exportkey) or [`SubtleCrypto.wrapKey()`](wrapkey).
-   `keyUsages` is an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) indicating what can be done with the newly generated key. Possible values for array elements are:
    -   `encrypt`: The key may be used to [`encrypt`](encrypt) messages.
    -   `decrypt`: The key may be used to [`decrypt`](decrypt) messages.
    -   `sign`: The key may be used to [`sign`](sign) messages.
    -   `verify`: The key may be used to [`verify`](verify) signatures.
    -   `deriveKey`: The key may be used in [`deriving a new key`](derivekey).
    -   `deriveBits`: The key may be used in [`deriving bits`](derivebits).
    -   `wrapKey`: The key may be used to [`wrap a key`](wrapkey).
    -   `unwrapKey`: The key may be used to [`unwrap a key`](unwrapkey).

### Return value

-   `result` is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a [`CryptoKey`](../cryptokey) (for symmetric algorithms) or a [`CryptoKeyPair`](../cryptokeypair) (for public-key algorithms).

### Exceptions

The promise is rejected when the following exception is encountered:

[`SyntaxError`](../domexception#exception-syntaxerror)  
Raised when the result is a [`CryptoKey`](../cryptokey) of type `secret` or `private` but *`keyUsages`* is empty.

[`SyntaxError`](../domexception#exception-syntaxerror)  
Raised when the result is a [`CryptoKeyPair`](../cryptokeypair) and its `privateKey.usages` attribute is empty.

Examples
--------

**Note**: You can [try the working examples](https://mdn.github.io/dom-examples/web-crypto/encrypt-decrypt/index.html) on GitHub.

### RSA key pair generation

This code generates an RSA-OAEP encryption key pair. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/rsa-oaep.js)

    let keyPair = window.crypto.subtle.generateKey(
      {
        name: "RSA-OAEP",
        modulusLength: 4096,
        publicExponent: new Uint8Array([1, 0, 1]),
        hash: "SHA-256"
      },
      true,
      ["encrypt", "decrypt"]
    );

### Elliptic curve key pair generation

This code generates an ECDSA signing key pair. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/ecdsa.js)

    let keyPair = window.crypto.subtle.generateKey(
      {
        name: "ECDSA",
        namedCurve: "P-384"
      },
      true,
      ["sign", "verify"]
    );

### HMAC key generation

This code generates an HMAC signing key. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/hmac.js)

    let key = window.crypto.subtle.generateKey(
      {
        name: "HMAC",
        hash: {name: "SHA-512"}
      },
      true,
      ["sign", "verify"]
    );

### AES key generation

This code generates an AES-GCM encryption key. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/aes-gcm.js)

    let key = window.crypto.subtle.generateKey(
      {
        name: "AES-GCM",
        length: 256
      },
      true,
      ["encrypt", "decrypt"]
    );

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-SubtleCrypto-method-generateKey">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.generateKey()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`generateKey`

37

12

\["Not supported: RSA-PSS, ECDSA, ECDH.", "Not supported: AES-CTR."\]

34

11

Returns `KeyOperation` instead of `Promise`

24

7

37

37

34

24

7

6.0

See also
--------

-   [Cryptographic key length recommendations](https://www.keylength.com/).
-   [NIST cryptographic algorithm and key length recommendations](https://csrc.nist.gov/publications/detail/sp/800-131a/rev-1/final).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/generateKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/generateKey</a>

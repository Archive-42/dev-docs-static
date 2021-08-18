SubtleCrypto.decrypt()
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `decrypt()` method of the [`SubtleCrypto`](../subtlecrypto) interface decrypts some encrypted data. It takes as arguments a [key](https://developer.mozilla.org/en-US/docs/Glossary/Key) to decrypt with, some optional extra parameters, and the data to decrypt (also known as "ciphertext"). It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which will be fulfilled with the decrypted data (also known as "plaintext").

Syntax
------

    const result = crypto.subtle.decrypt(algorithm, key, data);

### Parameters

-   *`algorithm`* is an object specifying the [algorithm](#supported_algorithms) to be used, and any extra parameters as required. The values given for the extra parameters must match those passed into the corresponding [`encrypt()`](encrypt) call.
    -   To use [RSA-OAEP](#rsa-oaep), pass an [`RsaOaepParams`](../rsaoaepparams) object.
    -   To use [AES-CTR](#aes-ctr), pass an [`AesCtrParams`](../aesctrparams) object.
    -   To use [AES-CBC](#aes-cbc), pass an [`AesCbcParams`](../aescbcparams) object.
    -   To use [AES-GCM](#aes-gcm), pass an [`AesGcmParams`](../aesgcmparams) object.
-   `key` is a [`CryptoKey`](../cryptokey) containing the key to be used for decryption. If using RSA-OAEP, this is the `privateKey` property of the [`CryptoKeyPair`](../cryptokeypair) object.
-   *`data`* is a [`BufferSource`](../buffersource) containing the data to be decrypted (also known as [ciphertext](https://developer.mozilla.org/en-US/docs/Glossary/Ciphertext)).

### Return value

-   `result` is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the plaintext.

### Exceptions

The promise is rejected when the following exceptions are encountered:

InvalidAccessError  
Raised when the requested operation is not valid for the provided key (e.g. invalid encryption algorithm, or invalid key for the specified encryption algorithm*)*.

OperationError  
Raised when the operation failed for an operation-specific reason (e.g. algorithm parameters of invalid sizes, or there was an error decrypting the ciphertext).

Supported algorithms
--------------------

The `decrypt()` method supports the same algorithms as the `encrypt()` method.

Examples
--------

**Note**: You can [try the working examples](https://mdn.github.io/dom-examples/web-crypto/encrypt-decrypt/index.html) on GitHub.

### RSA-OAEP

This code decrypts `ciphertext` using RSA-OAEP. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/rsa-oaep.js)

    function decryptMessage(privateKey, ciphertext) {
      return window.crypto.subtle.decrypt(
        {
          name: "RSA-OAEP"
        },
        privateKey,
        ciphertext
      );
    }

### AES-CTR

This code decrypts `ciphertext` using AES in CTR mode. Note that `counter` must match the value that was used for encryption. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/aes-ctr.js)

    function decryptMessage(key, ciphertext) {
      return window.crypto.subtle.decrypt(
        {
          name: "AES-CTR",
          counter,
          length: 64
        },
        key,
        ciphertext
      );
    }

### AES-CBC

This code decrypts `ciphertext` using AES in CBC mode. Note that `iv` must match the value that was used for encryption. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/aes-cbc.js)

    function decryptMessage(key, ciphertext) {
      return window.crypto.subtle.decrypt(
        {
          name: "AES-CBC",
          iv: iv
        },
        key,
        ciphertext
      );
    }

### AES-GCM

This code decrypts `ciphertext` using AES in GCM mode. Note that `iv` must match the value that was used for encryption. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/aes-gcm.js)

    function decryptMessage(key, ciphertext) {
      return window.crypto.subtle.decrypt(
        {
          name: "AES-GCM",
          iv: iv
        },
        key,
        ciphertext
      );
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#SubtleCrypto-method-decrypt">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.decrypt()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`decrypt`

37

12

Not supported: AES-CTR.

34

11

Returns `CryptoOperation` instead of `Promise`

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

-   [`SubtleCrypto.encrypt()`](encrypt).
-   [RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447) specifies RSAOAEP.
-   [NIST SP800-38A](https://csrc.nist.gov/publications/detail/sp/800-38a/final) specifies CTR mode.
-   [NIST SP800-38A](https://csrc.nist.gov/publications/detail/sp/800-38a/final) specifies CBC mode.
-   [NIST SP800-38D](https://csrc.nist.gov/publications/detail/sp/800-38d/final) specifies GCM mode.
-   [FIPS 198-1](https://csrc.nist.gov/csrc/media/publications/fips/198/1/final/documents/fips-198-1_final.pdf) specifies HMAC.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/decrypt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/decrypt</a>

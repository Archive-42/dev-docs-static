SubtleCrypto.sign()
===================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `sign()` method of the [`SubtleCrypto`](../subtlecrypto) interface generates a digital [signature](https://developer.mozilla.org/en-US/docs/Glossary/Signature).

It takes as its arguments a [key](https://developer.mozilla.org/en-US/docs/Glossary/Key) to sign with, some algorithm-specific parameters, and the data to sign. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which will be fulfilled with the signature.

You can use the corresponding [`SubtleCrypto.verify()`](verify) method to verify the signature.

Syntax
------

    const signature = crypto.subtle.sign(algorithm, key, data);

### Parameters

-   *`algorithm`* is a string or object that specifies the signature algorithm to use and its parameters:
    -   To use [RSASSA-PKCS1-v1\_5](#rsassa-pkcs1-v1_5), pass the string `"RSASSA-PKCS1-v1_5"` or an object of the form `{ "name": "RSASSA-PKCS1-v1_5" }`.
    -   To use [RSA-PSS](#rsa-pss), pass an [`RsaPssParams`](../rsapssparams) object.
    -   To use [ECDSA](#ecdsa), pass an [`EcdsaParams`](../ecdsaparams) object.
    -   To use [HMAC](#hmac), pass the string `"HMAC"` or an object of the form `{ "name": "HMAC" }`.
-   `key` is a [`CryptoKey`](../cryptokey) object containing the key to be used for signing. If algorithm identifies a public-key cryptosystem, this is the private key.
-   *`data`* is an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or [`ArrayBufferView`](../arraybufferview) object containing the data to be signed.

### Return value

-   `signature` is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the signature.

### Exceptions

The promise is rejected when the following exception is encountered:

[`InvalidAccessError`](../domexception#exception-invalidaccesserror)  
Raised when the signing key is not a key for the request signing algorithm or when trying to use an algorithm that is either unknown or isn't suitable for signing.

Supported algorithms
--------------------

The Web Crypto API provides four algorithms that can be used for signing and signature verification.

Three of these algorithms — RSASSA-PKCS1-v1\_5, RSA-PSS, and ECDSA — are [public-key cryptosystems](https://developer.mozilla.org/en-US/docs/Glossary/Public-key_cryptography) that use the private key for signing and the public key for verification. These systems all use a [digest algorithm](digest#supported_algorithms) to hash the message to a short fixed size before signing. The choice of digest algorithm is passed into the [`generateKey()`](generatekey) or [`importKey()`](importkey) functions.

The fourth algorithm — HMAC — uses the same algorithm and key for signing and for verification: this means that the verification key must be kept secret, which in turn means that this algorithm is not suitable for many signature use cases. It can be a good choice however when the signer and verifier are the same entity.

### RSASSA-PKCS1-v1\_5

The RSASSA-PKCS1-v1\_5 algorithm is specified in [RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447).

### RSA-PSS

The RSA-PSS algorithm is specified in [RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447).

It's different from RSASSA-PKCS1-v1\_5 in that it incorporates a random salt in the signature operation, so the same message signed with the same key will not result in the same signature each time. An extra property, defining the salt length, is passed into the [`sign()`](sign) and [`verify()`](verify) functions when they are invoked.

### ECDSA

ECDSA (Elliptic Curve Digital Signature Algorithm) is a variant of the Digital Signature Algorithm, specified in [FIPS-186](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.186-4.pdf), that uses Elliptic Curve Cryptography ([RFC 6090](https://datatracker.ietf.org/doc/html/rfc6090)).

### HMAC

The HMAC algorithm calculates and verifies hash-based message authentication codes according to the [FIPS 198-1 standard](https://csrc.nist.gov/csrc/media/publications/fips/198/1/final/documents/fips-198-1_final.pdf).

The digest algorithm to use is specified in the `HmacKeyGenParams` object that you pass into [`generateKey()`](generatekey), or the `HmacImportParams` object that you pass into [`importKey()`](importkey).

Examples
--------

**Note**: You can [try the working examples](https://mdn.github.io/dom-examples/web-crypto/sign-verify/index.html) out on GitHub.

### RSASSA-PKCS1-v1\_5

This code fetches the contents of a text box, encodes it for signing, and signs it with a private key. [See the complete source code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/rsassa-pkcs1.js)

    /*
    Fetch the contents of the "message" textbox, and encode it
    in a form we can use for the sign operation.
    */
    function getMessageEncoding() {
      const messageBox = document.querySelector(".rsassa-pkcs1 #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    let encoded = getMessageEncoding();
    let signature = await window.crypto.subtle.sign(
      "RSASSA-PKCS1-v1_5",
      privateKey,
      encoded
    );

### RSA-PSS

This code fetches the contents of a text box, encodes it for signing, and signs it with a private key. [See the complete source code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/rsa-pss.js)

    /*
    Fetch the contents of the "message" textbox, and encode it
    in a form we can use for the sign operation.
    */
    function getMessageEncoding() {
      const messageBox = document.querySelector(".rsa-pss #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    let encoded = getMessageEncoding();
    let signature = await window.crypto.subtle.sign(
      {
        name: "RSA-PSS",
        saltLength: 32,
      },
      privateKey,
      encoded
    );

### ECDSA

This code fetches the contents of a text box, encodes it for signing, and signs it with a private key. [See the complete source code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/ecdsa.js)

    /*
    Fetch the contents of the "message" textbox, and encode it
    in a form we can use for the sign operation.
    */
    function getMessageEncoding() {
      const messageBox = document.querySelector(".ecdsa #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    let encoded = getMessageEncoding();
    let signature = await window.crypto.subtle.sign(
      {
        name: "ECDSA",
        hash: {name: "SHA-384"},
      },
      privateKey,
      encoded
    );

### HMAC

This code fetches the contents of a text box, encodes it for signing, and signs it with a secret key. [See the complete source code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/hmac.js)

    /*
    Fetch the contents of the "message" textbox, and encode it
    in a form we can use for the sign operation.
    */
    function getMessageEncoding() {
      const messageBox = document.querySelector(".hmac #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    let encoded = getMessageEncoding();
    let signature = await window.crypto.subtle.sign(
      "HMAC",
      key,
      encoded
    );

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-SubtleCrypto-method-sign">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.sign()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`sign`

37

12

Not supported: RSA-PSS, ECDSA.

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

-   [`SubtleCrypto.verify()`](verify).
-   [RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447) specifies RSASSA-PKCS1-v1\_5.
-   [RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447) specifies RSA-PSS.
-   [FIPS-186](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.186-4.pdf) specifies ECDSA.
-   [FIPS 198-1](https://csrc.nist.gov/csrc/media/publications/fips/198/1/final/documents/fips-198-1_final.pdf) specifies HMAC.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/sign" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/sign</a>

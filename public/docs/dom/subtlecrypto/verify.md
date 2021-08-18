SubtleCrypto.verify()
=====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `verify()` method of the [`SubtleCrypto`](../subtlecrypto) interface verifies a digital [signature](https://developer.mozilla.org/en-US/docs/Glossary/Signature).

It takes as its arguments a [key](https://developer.mozilla.org/en-US/docs/Glossary/Key) to verify the signature with, some algorithm-specific parameters, the signature, and the original signed data. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which will be fulfilled with a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether the signature is valid.

Syntax
------

    const result = crypto.subtle.verify(algorithm, key, signature, data);

### Parameters

-   *`algorithm`* is a [`DOMString`](../domstring) or object defining the algorithm to use, and for some algorithm choices, some extra parameters. The values given for the extra parameters must match those passed into the corresponding [`sign()`](sign) call.
    -   To use [RSASSA-PKCS1-v1\_5](sign#rsassa-pkcs1-v1_5), pass the string `"RSASSA-PKCS1-v1_5"` or an object of the form `{ "name": "RSASSA-PKCS1-v1_5" }`.
    -   To use [RSA-PSS](sign#rsa-pss), pass an [`RsaPssParams`](../rsapssparams) object.
    -   To use [ECDSA](sign#ecdsa), pass an [`EcdsaParams`](../ecdsaparams) object.
    -   To use [HMAC](sign#hmac), pass the string `"HMAC"` or an object of the form `{ "name": "HMAC" }`.
-   `key` is a [`CryptoKey`](../cryptokey) containing the key that will be used to verify the signature. It is the secret key for a symmetric algorithm and the public key for a public-key system.
-   `signature` is a [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the [signature](https://developer.mozilla.org/en-US/docs/Glossary/Signature) to verify.
-   *`data`* is a [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the data whose signature is to be verified.

### Return value

-   `result` is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean): `true` if the signature is valid, `false` otherwise.

### Exceptions

The promise is rejected when the following exception is encountered:

[`InvalidAccessError`](../domexception#exception-invalidaccesserror)  
Raised when the encryption key is not a key for the requested verifying algorithm or when trying to use an algorithm that is either unknown or isn't suitable for a verify operation.

Supported algorithms
--------------------

The `verify()` method supports the same algorithms as the `sign()` method.

Examples
--------

**Note**: You can [try the working examples](https://mdn.github.io/dom-examples/web-crypto/sign-verify/index.html) out on GitHub.

### RSASSA-PKCS1-v1\_5

This code uses a public key to verify a signature. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/rsassa-pkcs1.js)

    /*
    Fetch the contents of the "message" textbox, and encode it
    in a form we can use for sign operation.
    */
    function getMessageEncoding() {
      const messageBox = document.querySelector(".rsassa-pkcs1 #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    /*
    Fetch the encoded message-to-sign and verify it against the stored signature.
    * If it checks out, set the "valid" class on the signature.
    * Otherwise set the "invalid" class.
    */
    async function verifyMessage(publicKey) {
      const signatureValue = document.querySelector(".rsassa-pkcs1 .signature-value");
      signatureValue.classList.remove("valid", "invalid");

      let encoded = getMessageEncoding();
      let result = await window.crypto.subtle.verify(
        "RSASSA-PKCS1-v1_5",
        publicKey,
        signature,
        encoded
      );

      signatureValue.classList.add(result ? "valid" : "invalid");
    }

### RSA-PSS

This code uses a public key to verify a signature. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/rsa-pss.js)

    /*
    Fetch the contents of the "message" textbox, and encode it
    in a form we can use for sign operation.
    */
    function getMessageEncoding() {
      const messageBox = document.querySelector(".rsa-pss #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    /*
    Fetch the encoded message-to-sign and verify it against the stored signature.
    * If it checks out, set the "valid" class on the signature.
    * Otherwise set the "invalid" class.
    */
    async function verifyMessage(publicKey) {
      const signatureValue = document.querySelector(".rsa-pss .signature-value");
      signatureValue.classList.remove("valid", "invalid");

      let encoded = getMessageEncoding();
      let result = await window.crypto.subtle.verify(
        {
          name: "RSA-PSS",
          saltLength: 32,
        },
        publicKey,
        signature,
        encoded
      );

      signatureValue.classList.add(result ? "valid" : "invalid");
    }

### ECDSA

This code uses a public key to verify a signature. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/ecdsa.js)

    /*
    Fetch the contents of the "message" textbox, and encode it
    in a form we can use for sign operation.
    */
    function getMessageEncoding() {
      const messageBox = document.querySelector(".ecdsa #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    /*
    Fetch the encoded message-to-sign and verify it against the stored signature.
    * If it checks out, set the "valid" class on the signature.
    * Otherwise set the "invalid" class.
    */
    async function verifyMessage(publicKey) {
      const signatureValue = document.querySelector(".ecdsa .signature-value");
      signatureValue.classList.remove("valid", "invalid");

      let encoded = getMessageEncoding();
      let result = await window.crypto.subtle.verify(
        {
          name: "ECDSA",
          hash: {name: "SHA-384"},
        },
        publicKey,
        signature,
        encoded
      );

      signatureValue.classList.add(result ? "valid" : "invalid");
    }

### HMAC

This code uses a secret key to verify a signature. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/sign-verify/hmac.js)

    /*
    Fetch the contents of the "message" textbox, and encode it
    in a form we can use for sign operation.
    */
    function getMessageEncoding() {
       const messageBox = document.querySelector(".hmac #message");
       let message = messageBox.value;
       let enc = new TextEncoder();
       return enc.encode(message);
    }

    /*
    Fetch the encoded message-to-sign and verify it against the stored signature.
    * If it checks out, set the "valid" class on the signature.
    * Otherwise set the "invalid" class.
    */
    async function verifyMessage(key) {
       const signatureValue = document.querySelector(".hmac .signature-value");
       signatureValue.classList.remove("valid", "invalid");

       let encoded = getMessageEncoding();
       let result = await window.crypto.subtle.verify(
         "HMAC",
         key,
         signature,
         encoded
       );

       signatureValue.classList.add(result ? "valid" : "invalid");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-SubtleCrypto-method-verify">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.verify()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`verify`

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

-   [`SubtleCrypto.sign()`](sign).
-   [RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447) specifies RSASSA-PKCS1-v1\_5.
-   [RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447) specifies RSA-PSS.
-   [FIPS-186](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.186-4.pdf) specifies ECDSA.
-   [FIPS 198-1](https://csrc.nist.gov/csrc/media/publications/fips/198/1/final/documents/fips-198-1_final.pdf) specifies HMAC.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/verify" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/verify</a>

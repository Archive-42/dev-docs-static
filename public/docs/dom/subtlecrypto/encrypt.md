SubtleCrypto.encrypt()
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `encrypt()` method of the [`SubtleCrypto`](../subtlecrypto) interface encrypts data.

It takes as its arguments a [key](https://developer.mozilla.org/en-US/docs/Glossary/Key) to encrypt with, some algorithm-specific parameters, and the data to encrypt (also known as "plaintext"). It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which will be fulfilled with the encrypted data (also known as "ciphertext").

Syntax
------

    const result = crypto.subtle.encrypt(algorithm, key, data);

### Parameters

-   *`algorithm`* is an object specifying the [algorithm](#supported_algorithms) to be used and any extra parameters if required:
    -   To use [RSA-OAEP](#rsa-oaep), pass an [`RsaOaepParams`](../rsaoaepparams) object.
    -   To use [AES-CTR](#aes-ctr), pass an [`AesCtrParams`](../aesctrparams) object.
    -   To use [AES-CBC](#aes-cbc), pass an [`AesCbcParams`](../aescbcparams) object.
    -   To use [AES-GCM](#aes-gcm), pass an [`AesGcmParams`](../aesgcmparams) object.
-   `key` is a [`CryptoKey`](../cryptokey) containing the key to be used for encryption.
-   *`data`* is a [`BufferSource`](../buffersource) containing the data to be encrypted (also known as the [plaintext](https://developer.mozilla.org/en-US/docs/Glossary/Plaintext)).

### Return value

-   `result` is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the "ciphertext".

### Exceptions

The promise is rejected when the following exceptions are encountered:

InvalidAccessError  
Raised when the requested operation is not valid for the provided key (e.g. invalid encryption algorithm, or invalid key for the specified encryption algorithm*)*.

OperationError  
Raised when the operation failed for an operation-specific reason (e.g. algorithm parameters of invalid sizes, or AES-GCM plaintext longer than 2³⁹−256 bytes).

Supported algorithms
--------------------

The Web Crypto API provides four algorithms that support the `encrypt()` and `decrypt()` operations.

One of these algorithms — RSA-OAEP — is a [public-key cryptosystem](https://developer.mozilla.org/en-US/docs/Glossary/Public-key_cryptography).

The other three encryption algorithms here are all [symmetric algorithms](https://developer.mozilla.org/en-US/docs/Glossary/Symmetric-key_cryptography), and they're all based on the same underlying cipher, AES (Advanced Encryption Standard). The difference between them is the [mode](https://developer.mozilla.org/en-US/docs/Glossary/Block_cipher_mode_of_operation). The Web Crypto API supports three different AES modes:

-   CTR (Counter Mode)
-   CBC (Cipher Block Chaining)
-   GCM (Galois/Counter Mode)

It's strongly recommended to use *authenticated encryption*, which includes checks that the ciphertext has not been modified by an attacker. Authentication helps protect against *chosen-ciphertext* attacks, in which an attacker can ask the system to decrypt arbitrary messages, and use the result to deduce information about the secret key. While it's possible to add authentication to CTR and CBC modes, they do not provide it by default and when implementing it manually one can easily make minor, but serious mistakes. GCM does provide built-in authentication, and for this reason it's often recommended over the other two AES modes.

### RSA-OAEP

The RSA-OAEP public-key encryption system is specified in [RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447).

### AES-CTR

This represents AES in Counter Mode, as specified in [NIST SP800-38A](https://csrc.nist.gov/publications/detail/sp/800-38a/final).

### AES-CBC

This represents AES in Cipher Block Chaining Mode, as specified in [NIST SP800-38A](https://csrc.nist.gov/publications/detail/sp/800-38a/final).

### AES-GCM

This represents AES in Galois/Counter Mode, as specified in [NIST SP800-38D](https://csrc.nist.gov/publications/detail/sp/800-38d/final).

One major difference between this mode and the others is that GCM is an "authenticated" mode, which means that it includes checks that the ciphertext has not been modified by an attacker.

Examples
--------

**Note**: You can [try the working examples](https://mdn.github.io/dom-examples/web-crypto/encrypt-decrypt/index.html) out on GitHub.

### RSA-OAEP

This code fetches the contents of a text box, encodes it for encryption, and encrypts it with using RSA-OAEP. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/rsa-oaep.js)

    function getMessageEncoding() {
      const messageBox = document.querySelector(".rsa-oaep #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    function encryptMessage(publicKey) {
      let encoded = getMessageEncoding();
      return window.crypto.subtle.encrypt(
        {
          name: "RSA-OAEP"
        },
        publicKey,
        encoded
      );
    }

### AES-CTR

This code fetches the contents of a text box, encodes it for encryption, and encrypts it using AES in CTR mode. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/aes-ctr.js)

    function getMessageEncoding() {
      const messageBox = document.querySelector(".aes-ctr #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    function encryptMessage(key) {
      let encoded = getMessageEncoding();
      // counter will be needed for decryption
      counter = window.crypto.getRandomValues(new Uint8Array(16));
      return window.crypto.subtle.encrypt(
        {
          name: "AES-CTR",
          counter,
          length: 64
        },
        key,
        encoded
      );
    }

    let iv = new Uint8Array(16);
    let key = new Uint8Array(16);
    let data = new Uint8Array(12345);
    //crypto functions are wrapped in promises so we have to use await and make sure the function that
    //contains this code is an async function
    //encrypt function wants a cryptokey object
    const key_encoded = await crypto.subtle.importKey(  "raw",    key.buffer,   'AES-CTR' ,  false,   ["encrypt", "decrypt"]);
    const encrypted_content = await window.crypto.subtle.encrypt(
        {
          name: "AES-CTR",
          counter: iv,
          length: 128
        },
        key_encoded,
        data
      );

    //Uint8Array
    console.log(encrypted_content);

### AES-CBC

This code fetches the contents of a text box, encodes it for encryption, and encrypts it using AES in CBC mode. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/aes-cbc.js)

    function getMessageEncoding() {
      const messageBox = document.querySelector(".aes-cbc #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    function encryptMessage(key) {
      let encoded = getMessageEncoding();
      // iv will be needed for decryption
      iv = window.crypto.getRandomValues(new Uint8Array(16));
      return window.crypto.subtle.encrypt(
        {
          name: "AES-CBC",
          iv
        },
        key,
        encoded
      );
    }

### AES-GCM

This code fetches the contents of a text box, encodes it for encryption, and encrypts it using AES in GCM mode. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/encrypt-decrypt/aes-gcm.js)

    function getMessageEncoding() {
      const messageBox = document.querySelector(".aes-gcm #message");
      let message = messageBox.value;
      let enc = new TextEncoder();
      return enc.encode(message);
    }

    function encryptMessage(key) {
      let encoded = getMessageEncoding();
      // iv will be needed for decryption
      iv = window.crypto.getRandomValues(new Uint8Array(12));
      return window.crypto.subtle.encrypt(
        {
          name: "AES-GCM",
          iv: iv
        },
        key,
        encoded
      );
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#SubtleCrypto-method-encrypt">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.encrypt()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`encrypt`

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

-   [`SubtleCrypto.decrypt()`](decrypt).
-   [RFC 3447](https://datatracker.ietf.org/doc/html/rfc3447) specifies RSAOAEP.
-   [NIST SP800-38A](https://csrc.nist.gov/publications/detail/sp/800-38a/final) specifies CTR mode.
-   [NIST SP800-38A](https://csrc.nist.gov/publications/detail/sp/800-38a/final) specifies CBC mode.
-   [NIST SP800-38D](https://csrc.nist.gov/publications/detail/sp/800-38d/final) specifies GCM mode.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/encrypt" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/encrypt</a>

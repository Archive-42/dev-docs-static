SubtleCrypto.wrapKey()
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `wrapKey()` method of the [`SubtleCrypto`](../subtlecrypto) interface "wraps" a key. This means that it exports the key in an external, portable format, then encrypts the exported key. Wrapping a key helps protect it in untrusted environments, such as inside an otherwise unprotected data store or in transmission over an unprotected network.

As with `SubtleCrypto.exportKey()`, you specify an [export format](importkey#supported_formats) for the key. To export a key, it must have [`CryptoKey.extractable`](../cryptokey) set to `true`.

But because `wrapKey()` also encrypts the key to be imported, you also need to pass in the key that must be used to encrypt it. This is sometimes called the "wrapping key".

The inverse of `wrapKey()` is [`SubtleCrypto.unwrapKey()`](unwrapkey): while `wrapKey` is composed of export + encrypt, `unwrapKey` is composed of import + decrypt.

Syntax
------

    const result = crypto.subtle.wrapKey(
        format,
        key,
        wrappingKey,
        wrapAlgo
    );

### Parameters

-   *`format`* is a string describing the data format in which the key will be exported before it is encrypted. It can be one of the following:
    -   `raw`: [Raw](importkey#raw) format.
    -   `pkcs8`: [PKCS \#8](importkey#pkcs_8) format.
    -   `spki`: [SubjectPublicKeyInfo](importkey#subjectpublickeyinfo) format.
    -   `jwk`: [JSON Web Key](importkey#json_web_key) format.
-   `key` is the [`CryptoKey`](../cryptokey) to wrap.
-   `wrappingkey` is the [`CryptoKey`](../cryptokey) used to encrypt the exported key. The key must have the `wrapKey` usage set.
-   `wrapAlgo` is an object specifying the [algorithm](encrypt#supported_algorithms) to be used to encrypt the exported key, and any required extra parameters:
    -   To use [RSA-OAEP](encrypt#rsa-oaep), pass an [`RsaOaepParams`](../rsaoaepparams) object.
    -   To use [AES-CTR](encrypt#aes-ctr), pass an [`AesCtrParams`](../aesctrparams) object.
    -   To use [AES-CBC](encrypt#aes-cbc), pass an [`AesCbcParams`](../aescbcparams) object.
    -   To use [AES-GCM](encrypt#aes-gcm), pass an [`AesGcmParams`](../aesgcmparams) object.
    -   To use [AES-KW](#AES-KW), pass the string `"AES-KW"`, or an object of the form `{ "name": "AES-KW }`.

### Return value

-   `result` is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with an `ArrayBuffer` containing the encrypted exported key.

### Exceptions

The promise is rejected when one of the following exceptions is encountered:

[`InvalidAccessError`](../domexception#exception-invalidaccesserror)  
Raised when the wrapping key is not a key for the requested wrap algorithm.

[`NotSupported`](../domexception#exception-notsupported)  
Raised when trying to use an algorithm that is either unknown or isn't suitable for encryption or wrapping.

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Raised when trying to use an invalid format.

Supported algorithms
--------------------

All [algorithms that are usable for encryption](encrypt#supported_algorithms) are also usable for key wrapping, as long as the key has the "wrapKey" usage set. For key wrapping you have the additional option of AES-KW.

### AES-KW

AES-KW is a way to use the AES cipher for key wrapping.

One advantage of using AES-KW over another AES mode such as AES-GCM is that AES-KW does not require an initialization vector. To use AES-KW, the input must be a multiple of 64 bits.

AES-KW is specified in [RFC 3394](https://datatracker.ietf.org/doc/html/rfc3394).

Examples
--------

**Note**: You can [try the working examples](https://mdn.github.io/dom-examples/web-crypto/wrap-key/index.html) out on GitHub.

### <span class="highlight-span">Raw wrap</span>

This example wraps an AES key. It uses "raw" as the export format and AES-KW, with a password-derived key, to encrypt it. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/wrap-key/raw.js)

    let salt;

    /*
    Get some key material to use as input to the deriveKey method.
    The key material is a password supplied by the user.
    */
    function getKeyMaterial() {
      const password = window.prompt("Enter your password");
      const enc = new TextEncoder();
      return window.crypto.subtle.importKey(
        "raw",
        enc.encode(password),
        {name: "PBKDF2"},
        false,
        ["deriveBits", "deriveKey"]
      );
    }

    /*
    Given some key material and some random salt
    derive an AES-KW key using PBKDF2.
    */
    function getKey(keyMaterial, salt) {
      return window.crypto.subtle.deriveKey(
        {
          "name": "PBKDF2",
          salt: salt,
          "iterations": 100000,
          "hash": "SHA-256"
        },
        keyMaterial,
        { "name": "AES-KW", "length": 256},
        true,
        [ "wrapKey", "unwrapKey" ]
      );
    }

    /*
    Wrap the given key.
    */
    async function wrapCryptoKey(keyToWrap) {
      // get the key encryption key
      const keyMaterial = await getKeyMaterial();
      salt = window.crypto.getRandomValues(new Uint8Array(16));
      const wrappingKey = await getKey(keyMaterial, salt);

      return window.crypto.subtle.wrapKey(
        "raw",
        keyToWrap,
        wrappingKey,
        "AES-KW"
      );

    }

    /*
    Generate an encrypt/decrypt secret key,
    then wrap it.
    */
    window.crypto.subtle.generateKey(
      {
        name: "AES-GCM",
        length: 256,
      },
      true,
      ["encrypt", "decrypt"]
    )
    .then((secretKey) => {
      return wrapCryptoKey(secretKey);
    })
    .then((wrappedKey) => {
      console.log(wrappedKey);
    });

### <span class="highlight-span">PKCS \#8 wrap</span>

This example wraps an RSA private signing key. It uses "pkcs8" as the export format and AES-GCM, with a password-derived key, to encrypt it. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/wrap-key/pkcs8.js)

    let salt;
    let iv;

    /*
    Get some key material to use as input to the deriveKey method.
    The key material is a password supplied by the user.
    */
    function getKeyMaterial() {
      const password = window.prompt("Enter your password");
      const enc = new TextEncoder();
      return window.crypto.subtle.importKey(
        "raw",
        enc.encode(password),
        {name: "PBKDF2"},
        false,
        ["deriveBits", "deriveKey"]
      );
    }

    /*
    Given some key material and some random salt
    derive an AES-GCM key using PBKDF2.
    */
    function getKey(keyMaterial, salt) {
      return window.crypto.subtle.deriveKey(
        {
          "name": "PBKDF2",
          salt: salt,
          "iterations": 100000,
          "hash": "SHA-256"
        },
        keyMaterial,
        { "name": "AES-GCM", "length": 256},
        true,
        [ "wrapKey", "unwrapKey" ]
      );
    }

    /*
    Wrap the given key.
    */
    async function wrapCryptoKey(keyToWrap) {
      // get the key encryption key
      const keyMaterial = await getKeyMaterial();
      salt = window.crypto.getRandomValues(new Uint8Array(16));
      const wrappingKey = await getKey(keyMaterial, salt);
      iv = window.crypto.getRandomValues(new Uint8Array(12));

      return window.crypto.subtle.wrapKey(
        "pkcs8",
        keyToWrap,
        wrappingKey,
        {
          name: "AES-GCM",
          iv: iv
        }
      );

    }

    /*
    Generate a sign/verify key pair,
    then wrap the private key.
    */
    window.crypto.subtle.generateKey(
      {
        name: "RSA-PSS",
        // Consider using a 4096-bit key for systems that require long-term security
        modulusLength: 2048,
        publicExponent: new Uint8Array([1, 0, 1]),
        hash: "SHA-256",
      },
      true,
      ["sign", "verify"]
    )
    .then((keyPair) => {
      return wrapCryptoKey(keyPair.privateKey);
    })
    .then((wrappedKey) => {
      console.log(wrappedKey);
    });

### <span class="highlight-span">SubjectPublicKeyInfo wrap</span>

This example wraps an RSA public encryption key. It uses "spki" as the export format and AES-CBC, with a password-derived key, to encrypt it. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/wrap-key/spki.js)

    let salt;
    let iv;

    /*
    Get some key material to use as input to the deriveKey method.
    The key material is a password supplied by the user.
    */
    function getKeyMaterial() {
      const password = window.prompt("Enter your password");
      const enc = new TextEncoder();
      return window.crypto.subtle.importKey(
        "raw",
        enc.encode(password),
        {name: "PBKDF2"},
        false,
        ["deriveBits", "deriveKey"]
      );
    }

    /*
    Given some key material and some random salt
    derive an AES-CBC key using PBKDF2.
    */
    function getKey(keyMaterial, salt) {
      return window.crypto.subtle.deriveKey(
        {
          "name": "PBKDF2",
          salt: salt,
          "iterations": 100000,
          "hash": "SHA-256"
        },
        keyMaterial,
        { "name": "AES-CBC", "length": 256},
        true,
        [ "wrapKey", "unwrapKey" ]
      );
    }

    /*
    Wrap the given key.
    */
    async function wrapCryptoKey(keyToWrap) {
      // get the key encryption key
      const keyMaterial = await getKeyMaterial();
      salt = window.crypto.getRandomValues(new Uint8Array(16));
      const wrappingKey = await getKey(keyMaterial, salt);
      iv = window.crypto.getRandomValues(new Uint8Array(16));

      return window.crypto.subtle.wrapKey(
        "spki",
        keyToWrap,
        wrappingKey,
        {
          name: "AES-CBC",
          iv: iv
        }
      );

    }

    /*
    Generate an encrypt/decrypt key pair,
    then wrap it.
    */
    window.crypto.subtle.generateKey(
      {
        name: "RSA-OAEP",
        // Consider using a 4096-bit key for systems that require long-term security
        modulusLength: 2048,
        publicExponent: new Uint8Array([1, 0, 1]),
        hash: "SHA-256",
      },
      true,
      ["encrypt", "decrypt"]
    )
    .then((keyPair) => {
      return wrapCryptoKey(keyPair.publicKey);
    })
    .then((wrappedKey) => {
      console.log(wrappedKey);
    });

### <span class="highlight-span">JSON Web Key import</span>

This code wraps an ECDSA private signing key. It uses "jwk" as the export format and AES-GCM, with a password-derived key, to encrypt it. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/wrap-key/jwk.js)

    let salt;
    let iv;

    /*
    Get some key material to use as input to the deriveKey method.
    The key material is a password supplied by the user.
    */
    function getKeyMaterial() {
      const password = window.prompt("Enter your password");
      const enc = new TextEncoder();
      return window.crypto.subtle.importKey(
        "raw",
        enc.encode(password),
        {name: "PBKDF2"},
        false,
        ["deriveBits", "deriveKey"]
      );
    }

    /*
    Given some key material and some random salt
    derive an AES-GCM key using PBKDF2.
    */
    function getKey(keyMaterial, salt) {
      return window.crypto.subtle.deriveKey(
        {
          "name": "PBKDF2",
          salt: salt,
          "iterations": 100000,
          "hash": "SHA-256"
        },
        keyMaterial,
        { "name": "AES-GCM", "length": 256},
        true,
        [ "wrapKey", "unwrapKey" ]
      );
    }

    /*
    Wrap the given key.
    */
    async function wrapCryptoKey(keyToWrap) {
      // get the key encryption key
      const keyMaterial = await getKeyMaterial();
      salt = window.crypto.getRandomValues(new Uint8Array(16));
      const wrappingKey = await getKey(keyMaterial, salt);
      iv = window.crypto.getRandomValues(new Uint8Array(12));

      return window.crypto.subtle.wrapKey(
        "jwk",
        keyToWrap,
        wrappingKey,
        {
          name: "AES-GCM",
          iv: iv
        }
      );
    }

    /*
    Generate a sign/verify key pair,
    then wrap the private key
    */
    window.crypto.subtle.generateKey(
      {
        name: "ECDSA",
        namedCurve: "P-384"
      },
      true,
      ["sign", "verify"]
    )
    .then((keyPair) => {
      return wrapCryptoKey(keyPair.privateKey);
    })
    .then((wrappedKey) => {
      console.log(wrappedKey);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-SubtleCrypto-method-wrapKey">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.wrapKey()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`wrapKey`

37

12

Not supported: AES-CTR.

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

-   `SubtleCrypto.exportKey()`
-   [PKCS \#8 format](https://datatracker.ietf.org/doc/html/rfc5208).
-   [SubjectPublicKeyInfo format](https://datatracker.ietf.org/doc/html/rfc5280#section-4.1).
-   [JSON Web Key format](https://datatracker.ietf.org/doc/html/rfc7517).
-   [AES-KW specification](https://datatracker.ietf.org/doc/html/rfc3394).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/wrapKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/wrapKey</a>

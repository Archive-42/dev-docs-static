SubtleCrypto.deriveBits()
=========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `deriveBits()` method of the [`SubtleCrypto`](../subtlecrypto) interface can be used to derive an array of bits from a base key.

It takes as its arguments the base key, the derivation algorithm to use, and the length of the bit string to derive. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which will be fulfilled with an `ArrayBuffer` containing the derived bits.

This method is very similar to `SubtleCrypto.deriveKey()`, except that `deriveKey()` returns a `CryptoKey` object rather than an `ArrayBuffer`. Essentially `deriveKey()` is composed of `deriveBits()` followed by `importKey()`.

This function supports the same derivation algorithms as `deriveKey()`: ECDH, HKDF, and PBKDF2. See [Supported algorithms](derivekey#supported_algorithms) for some more detail on these algorithms.

Syntax
------

    const result = crypto.subtle.deriveBits(
        algorithm,
        baseKey,
        length
    );

### Parameters

-   `algorithm` is an object defining the [derivation algorithm](derivekey#supported_algorithms) to use.
    -   To use [ECDH](derivekey#ecdh), pass an `EcdhKeyDeriveParams` object.
    -   To use [HKDF](derivekey#hkdf), pass an `HkdfParams` object.
    -   To use [PBKDF2](derivekey#pbkdf2), pass a `Pbkdf2Params` object.
-   *`baseKey`* is a [`CryptoKey`](../cryptokey) representing the input to the derivation algorithm. If `algorithm` is ECDH, this will be the ECDH private key. Otherwise it will be the initial key material for the derivation function: for example, for PBKDF2 it might be a password, imported as a `CryptoKey` using `SubtleCrypto.importKey()`.
-   `length` is a number representing the number of bits to derive.

### Return value

-   `result` is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the derived bits.

### Exceptions

The promise is rejected when one of the following exceptions are encountered:

[`InvalidAccessError`](../domexception#exception-invalidaccesserror)  
Raised when the base key is not a key for the requested derivation algorithm or if the [`CryptoKey.usages`](../cryptokey) value of that key doesn't contain `deriveKey`.

[`NotSupported`](../domexception#exception-notsupported)  
Raised when trying to use an algorithm that is either unknown or isn't suitable for derivation, or if the algorithm requested for the derived key doesn't define a key length.

Supported algorithms
--------------------

See the [Supported algorithms section of the `deriveKey()` documentation](derivekey#supported_algorithms).

Examples
--------

**Note**: You can [try the working examples](https://mdn.github.io/dom-examples/web-crypto/derive-bits/index.html) on GitHub.

### ECDH

In this example Alice and Bob each generate an ECDH key pair.

We then use Alice's private key and Bob's public key to derive a shared secret. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/derive-bits/ecdh.js)

    async function deriveSharedSecret(privateKey, publicKey) {
      const sharedSecret = await window.crypto.subtle.deriveBits(
        {
          name: "ECDH",
          namedCurve: "P-384",
          public: publicKey
        },
        privateKey,
        128
      );

      const buffer = new Uint8Array(sharedSecret, 0, 5);
      const sharedSecretValue = document.querySelector(".ecdh .derived-bits-value");
      sharedSecretValue.classList.add("fade-in");
      sharedSecretValue.addEventListener("animationend", () => {
        sharedSecretValue.classList.remove("fade-in");
      });
      sharedSecretValue.textContent = `${buffer}...[${sharedSecret.byteLength} bytes total]`;
    }

    // Generate 2 ECDH key pairs: one for Alice and one for Bob
    // In more normal usage, they would generate their key pairs
    // separately and exchange public keys securely
    const generateAlicesKeyPair = window.crypto.subtle.generateKey(
      {
        name: "ECDH",
        namedCurve: "P-384"
      },
      false,
      ["deriveBits"]
    );

    const generateBobsKeyPair = window.crypto.subtle.generateKey(
      {
        name: "ECDH",
        namedCurve: "P-384"
      },
      false,
      ["deriveBits"]
    );

    Promise.all([generateAlicesKeyPair, generateBobsKeyPair]).then(values => {
      const alicesKeyPair = values[0];
      const bobsKeyPair = values[1];

      const deriveBitsButton = document.querySelector(".ecdh .derive-bits-button");
      deriveBitsButton.addEventListener("click", () => {
        // Alice then generates a secret using her private key and Bob's public key.
        // Bob could generate the same secret using his private key and Alice's public key.
        deriveSharedSecret(alicesKeyPair.privateKey, bobsKeyPair.publicKey);
      });
    });

### PBKDF2

In this example we ask the user for a password, then use it to derive some bits using PBKDF2. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/derive-bits/pbkdf2.js)

    let salt;

    /*
    Get some key material to use as input to the deriveBits method.
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
    Derive some bits from a password supplied by the user.
    */
    async function getDerivedBits() {
      const keyMaterial = await getKeyMaterial();
      salt = window.crypto.getRandomValues(new Uint8Array(16));
      const derivedBits = await window.crypto.subtle.deriveBits(
        {
          "name": "PBKDF2",
          salt: salt,
          "iterations": 100000,
          "hash": "SHA-256"
        },
        keyMaterial,
        256
      );

      const buffer = new Uint8Array(derivedBits, 0, 5);
      const derivedBitsValue = document.querySelector(".pbkdf2 .derived-bits-value");
      derivedBitsValue.classList.add("fade-in");
      derivedBitsValue.addEventListener("animationend", () => {
        derivedBitsValue.classList.remove("fade-in");
      });
      derivedBitsValue.textContent = `${buffer}...[${derivedBits.byteLength} bytes total]`;
    }

    const deriveBitsButton = document.querySelector(".pbkdf2 .derive-bits-button");
    deriveBitsButton.addEventListener("click", () => {
      getDerivedBits();
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-SubtleCrypto-method-deriveBits">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.deriveBits()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`deriveBits`

37

12

\["Not supported: ECDH.", "Not supported: HKDF, PBKDF2."\]

34

No

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

-   [HKDF specification](https://datatracker.ietf.org/doc/html/rfc5869).
-   [NIST guidelines for password-based key derivation](https://csrc.nist.gov/publications/detail/sp/800-132/final).
-   [Password storage cheat sheet](https://www.owasp.org/index.php/Password_Storage_Cheat_Sheet).
-   [Advice on choosing an iteration count for PBKDF2](https://security.stackexchange.com/questions/3959/recommended-of-iterations-when-using-pkbdf2-sha256/3993#3993).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/deriveBits" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/deriveBits</a>

SubtleCrypto.exportKey()
========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `exportKey()` method of the [`SubtleCrypto`](../subtlecrypto) interface exports a key: that is, it takes as input a [`CryptoKey`](../cryptokey) object and gives you the key in an external, portable format.

To export a key, the key must have [`CryptoKey.extractable`](../cryptokey) set to `true`.

Keys can be exported in several formats: see [Supported formats](importkey#supported_formats) in the `SubtleCrypto.importKey()` page for details.

Keys are not exported in an encrypted format: to encrypt keys when exporting them use the `SubtleCrypto.wrapKey()` API instead.

Syntax
------

    const result = crypto.subtle.exportKey(format, key);

### Parameters

-   *`format`* is a string value describing the data format in which the key should be exported. It can be one of the following:
    -   `raw`: [Raw](importkey#raw) format.
    -   `pkcs8`: [PKCS \#8](importkey#pkcs_8) format.
    -   `spki`: [SubjectPublicKeyInfo](importkey#subjectpublickeyinfo) format.
    -   `jwk`: [JSON Web Key](importkey#json_web_key) format.
-   `key` is the [`CryptoKey`](../cryptokey) to export.

### Return value

-   `result` is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).
    -   If `format` was `jwk`, then the promise fulfills with a JSON object containing the key.
    -   Otherwise the promise fulfills with an `ArrayBuffer` containing the key.

### Exceptions

The promise is rejected when one of the following exceptions is encountered:

[`InvalidAccessError`](../domexception#exception-invalidaccesserror)  
Raised when trying to export a non-extractable key.

[`NotSupported`](../domexception#exception-notsupported)  
Raised when trying to export in an unknown format.

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Raised when trying to use an invalid format.

Examples
--------

**Note**: You can [try the working examples](https://mdn.github.io/dom-examples/web-crypto/export-key/index.html) out on GitHub.

### <span class="highlight-span">Raw export</span>

This example exports an AES key as an `ArrayBuffer` containing the bytes for the key. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/export-key/raw.js)

    /*
    Export the given key and write it into the "exported-key" space.
    */
    async function exportCryptoKey(key) {
      const exported = await window.crypto.subtle.exportKey(
        "raw",
        key
      );
      const exportedKeyBuffer = new Uint8Array(exported);

      const exportKeyOutput = document.querySelector(".exported-key");
      exportKeyOutput.textContent = `[${exportedKeyBuffer}]`;
    }

    /*
    Generate an encrypt/decrypt secret key,
    then set up an event listener on the "Export" button.
    */
    window.crypto.subtle.generateKey(
      {
        name: "AES-GCM",
        length: 256,
      },
      true,
      ["encrypt", "decrypt"]
    ).then((key) => {
      const exportButton = document.querySelector(".raw");
      exportButton.addEventListener("click", () => {
        exportCryptoKey(key);
      });
    });

### <span class="highlight-span">PKCS \#8 export</span>

This example exports an RSA private signing key as a PKCS \#8 object. The exported key is then PEM-encoded. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/export-key/pkcs8.js)

    /*
    Convert  an ArrayBuffer into a string
    from https://developers.google.com/web/updates/2012/06/How-to-convert-ArrayBuffer-to-and-from-String
    */
    function ab2str(buf) {
      return String.fromCharCode.apply(null, new Uint8Array(buf));
    }

    /*
    Export the given key and write it into the "exported-key" space.
    */
    async function exportCryptoKey(key) {
      const exported = await window.crypto.subtle.exportKey(
        "pkcs8",
        key
      );
      const exportedAsString = ab2str(exported);
      const exportedAsBase64 = window.btoa(exportedAsString);
      const pemExported = `-----BEGIN PRIVATE KEY-----\n${exportedAsBase64}\n-----END PRIVATE KEY-----`;

      const exportKeyOutput = document.querySelector(".exported-key");
      exportKeyOutput.textContent = pemExported;
    }

    /*
    Generate a sign/verify key pair,
    then set up an event listener on the "Export" button.
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
    ).then((keyPair) => {
      const exportButton = document.querySelector(".pkcs8");
      exportButton.addEventListener("click", () => {
        exportCryptoKey(keyPair.privateKey);
      });

    });

### <span class="highlight-span">SubjectPublicKeyInfo export</span>

This example exports an RSA public encryption key as a PEM-encoded SubjectPublicKeyInfo object. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/export-key/spki.js)

    /*
    Convert  an ArrayBuffer into a string
    from https://developers.google.com/web/updates/2012/06/How-to-convert-ArrayBuffer-to-and-from-String
    */
    function ab2str(buf) {
      return String.fromCharCode.apply(null, new Uint8Array(buf));
    }

    /*
    Export the given key and write it into the "exported-key" space.
    */
    async function exportCryptoKey(key) {
      const exported = await window.crypto.subtle.exportKey(
        "spki",
        key
      );
      const exportedAsString = ab2str(exported);
      const exportedAsBase64 = window.btoa(exportedAsString);
      const pemExported = `-----BEGIN PUBLIC KEY-----\n${exportedAsBase64}\n-----END PUBLIC KEY-----`;

      const exportKeyOutput = document.querySelector(".exported-key");
      exportKeyOutput.textContent = pemExported;
    }

    /*
    Generate an encrypt/decrypt key pair,
    then set up an event listener on the "Export" button.
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
    ).then((keyPair) => {
      const exportButton = document.querySelector(".spki");
      exportButton.addEventListener("click", () => {
        exportCryptoKey(keyPair.publicKey);
      });
    });

### <span class="highlight-span">JSON Web Key export</span>

This code exports an ECDSA private signing key as a JSON Web Key object. [See the complete code on GitHub.](https://github.com/mdn/dom-examples/blob/master/web-crypto/export-key/jwk.js)

    /*
    Export the given key and write it into the "exported-key" space.
    */
    async function exportCryptoKey(key) {
      const exported = await window.crypto.subtle.exportKey(
        "jwk",
        key
      );
      const exportKeyOutput = document.querySelector(".exported-key");
      exportKeyOutput.textContent = JSON.stringify(exported, null, " ");
     }

    /*
    Generate a sign/verify key pair,
    then set up an event listener on the "Export" button.
    */
    window.crypto.subtle.generateKey(
      {
        name: "ECDSA",
        namedCurve: "P-384"
      },
      true,
      ["sign", "verify"]
    ).then((keyPair) => {
      const exportButton = document.querySelector(".jwk");
      exportButton.addEventListener("click", () => {
        exportCryptoKey(keyPair.privateKey);
      });

    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-SubtleCrypto-method-exportKey">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.exportKey()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`exportKey`

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

-   `SubtleCrypto.importKey()`
-   `SubtleCrypto.wrapKey()`
-   [PKCS \#8 format](https://datatracker.ietf.org/doc/html/rfc5208).
-   [SubjectPublicKeyInfo format](https://datatracker.ietf.org/doc/html/rfc5280#section-4.1).
-   [JSON Web Key format](https://datatracker.ietf.org/doc/html/rfc7517).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/exportKey" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/exportKey</a>

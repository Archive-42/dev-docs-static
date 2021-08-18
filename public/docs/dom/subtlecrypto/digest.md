SubtleCrypto.digest()
=====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `digest()` method of the [`SubtleCrypto`](../subtlecrypto) interface generates a [digest](https://developer.mozilla.org/en-US/docs/Glossary/Digest) of the given data. A digest is a short fixed-length value derived from some variable-length input. Cryptographic digests should exhibit collision-resistance, meaning that it's hard to come up with two different inputs that have the same digest value.

It takes as its arguments an identifier for the digest algorithm to use and the data to digest. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which will be fulfilled with the digest.

Syntax
------

    const digest = crypto.subtle.digest(algorithm, data);

### Parameters

-   `algorithm` is a [`DOMString`](../domstring) defining the hash function to use. Supported values are:
    -   `SHA-1` (but don't use this in cryptographic applications)
    -   `SHA-256`
    -   `SHA-384`
    -   `SHA-512`.
-   `data` is an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or [`ArrayBufferView`](../arraybufferview) containing the data to be digested.

### Return value

-   `digest` is a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the digest.

Supported algorithms
--------------------

Digest algorithms, also known as [cryptographic hash functions](https://developer.mozilla.org/en-US/docs/Glossary/Cryptographic_hash_function), transform an arbitrarily large block of data into a fixed-size output, usually much shorter than the input. They have a variety of applications in cryptography.

<table><thead><tr class="header"><th>Algorithm</th><th>Output length (bits)</th><th>Block size (bits)</th><th>Specification</th></tr></thead><tbody><tr class="odd"><td>SHA-1</td><td>160</td><td>512</td><td><a href="https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf">FIPS 180-4</a>, section 6.1</td></tr><tr class="even"><td>SHA-256</td><td>256</td><td>512</td><td><a href="https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf">FIPS 180-4</a>, section 6.2</td></tr><tr class="odd"><td>SHA-384</td><td>384</td><td>1024</td><td><a href="https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf">FIPS 180-4</a>, section 6.5</td></tr><tr class="even"><td>SHA-512</td><td>512</td><td>1024</td><td><a href="https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf">FIPS 180-4</a>, section 6.4</td></tr></tbody></table>

**Warning**: SHA-1 is now considered vulnerable and should not be used for cryptographic applications.

Hint: If you are looking here for how to create an keyed-hash message authentication code ([HMAC](https://developer.mozilla.org/en-US/docs/Glossary/HMAC)), you need to use the [SubtleCrypto.sign()](sign#hmac) instead.

Examples
--------

### Basic example

This example encodes a message, then calculates its SHA-256 digest and logs the digest length:

    const text = 'An obscure body in the S-K System, your majesty. The inhabitants refer to it as the planet Earth.';

    async function digestMessage(message) {
      const encoder = new TextEncoder();
      const data = encoder.encode(message);
      const hash = await crypto.subtle.digest('SHA-256', data);
      return hash;
    }

    const digestBuffer = await digestMessage(text);
    console.log(digestBuffer.byteLength);

### Converting a digest to a hex string

The digest is returned as an `ArrayBuffer`, but for comparison and display digests are often represented as hex strings. This example calculates a digest, then converts the `ArrayBuffer` to a hex string:

    const text = 'An obscure body in the S-K System, your majesty. The inhabitants refer to it as the planet Earth.';

    async function digestMessage(message) {
      const msgUint8 = new TextEncoder().encode(message);                           // encode as (utf-8) Uint8Array
      const hashBuffer = await crypto.subtle.digest('SHA-256', msgUint8);           // hash the message
      const hashArray = Array.from(new Uint8Array(hashBuffer));                     // convert buffer to byte array
      const hashHex = hashArray.map(b => b.toString(16).padStart(2, '0')).join(''); // convert bytes to hex string
      return hashHex;
    }

    const digestHex = await digestMessage(text);
    console.log(digestHex);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-SubtleCrypto-method-digest">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.digest()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`digest`

37

12

Not supported: SHA-1.

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

In Chrome 60, they added a feature that disables crypto.subtle for non-TLS connections.

See also
--------

-   [Chromium secure origins specification](https://www.chromium.org/Home/chromium-security/prefer-secure-origins-for-powerful-new-features)
-   [FIPS 180-4](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf) specifies the SHA family of digest algorithms.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/digest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/digest</a>

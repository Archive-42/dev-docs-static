EcdsaParams
===========

The `EcdsaParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.sign()`](subtlecrypto/sign) or [`SubtleCrypto.verify()`](subtlecrypto/verify) when using the [ECDSA](subtlecrypto/sign#ecdsa) algorithm.

Properties
----------

`name`  
A [`DOMString`](domstring). This should be set to `ECDSA`.

`hash`  
A [`DOMString`](domstring). An identifier for the [digest algorithm](subtlecrypto/digest) to use. This should be one of the following:

-   `SHA-256`: selects the [SHA-256](subtlecrypto/digest#sha-256) algorithm.
-   `SHA-384`: selects the [SHA-384](subtlecrypto/digest#sha-384) algorithm.
-   `SHA-512`: selects the [SHA-512](subtlecrypto/digest#sha-512) algorithm.

**Warning**: `SHA-1` is also supported here but the [SHA-1](subtlecrypto/digest#sha-1) algorithm is considered vulnerable and should no longer be used.

Examples
--------

See the examples for [`SubtleCrypto.sign()`](subtlecrypto/sign) or [`SubtleCrypto.verify()`](subtlecrypto/verify).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-EcdsaParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.EcdsaParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`EcdsaParams`

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

Browsers that support the "ECDSA" algorithm for the [`SubtleCrypto.sign()`](subtlecrypto/sign) and [`SubtleCrypto.verify()`](subtlecrypto/verify) methods will support this type.

See also
--------

-   [`SubtleCrypto.sign()`](subtlecrypto/sign) and [`SubtleCrypto.verify()`](subtlecrypto/verify).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EcdsaParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EcdsaParams</a>

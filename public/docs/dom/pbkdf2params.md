Pbkdf2Params
============

The `Pbkdf2Params` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey), when using the [PBKDF2](subtlecrypto/derivekey#pbkdf2) algorithm.

Properties
----------

`name`  
A [`DOMString`](domstring). This should be set to `PBKDF2`.

`hash`  
A [`DOMString`](domstring) representing the [digest algorithm](subtlecrypto/digest#supported_algorithms) to use. This may be one of:

-   `SHA-1`
-   `SHA-256`
-   `SHA-384`
-   `SHA-512`

**Warning**: `SHA-1` is considered vulnerable in most cryptographic applications, but is still considered safe in PBKDF2. However, it's advisable to transition away from it everywhere, so unless you need to use `SHA-1`, don't. Use a different digest algorithm instead.

`salt`  
A [`BufferSource`](buffersource). This should be a random or pseudo-random value of at least 16 bytes. Unlike the input key material passed into `deriveKey()`, `salt` does not need to be kept secret.

`iterations`  
A `Number` representing the number of times the hash function will be executed in `deriveKey()`. This determines how computationally expensive (that is, slow) the `deriveKey()` operation will be. In this context, slow is good, since it makes it more expensive for an attacker to run a <span class="page-not-created">dictionary attack</span> against the keys. The general guidance here is to use as many iterations as possible, subject to keeping an acceptable level of performance for your application.

Examples
--------

See the examples for [`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-Pbkdf2Params">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.Pbkdf2Params' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

See also
--------

-   [`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Pbkdf2Params" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Pbkdf2Params</a>

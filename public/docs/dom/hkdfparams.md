HkdfParams
==========

The `HkdfParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey), when using the [HKDF](subtlecrypto/derivekey#hkdf) algorithm.

Properties
----------

`name`  
A [`DOMString`](domstring). This should be set to `HKDF`.

`hash`  
A [`DOMString`](domstring) representing the [digest algorithm](subtlecrypto/digest#supported_algorithms) to use. This may be one of:

-   `SHA-1`
-   `SHA-256`
-   `SHA-384`
-   `SHA-512`

`salt`  
A [`BufferSource`](buffersource). The [HKDF specification](https://datatracker.ietf.org/doc/html/rfc5869) states that adding salt "adds significantly to the strength of HKDF". Ideally, the salt is a random or pseudo-random value with the same length as the output of the digest function. Unlike the input key material passed into `deriveKey()`, salt does not need to be kept secret.

`info`  
A [`BufferSource`](buffersource) representing application-specific contextual information. This is used to bind the derived key to an application or context, and enables you to derive different keys for different contexts while using the same input key material. It's important that this should be independent of the input key material itself. This property is required but may be an empty buffer.

Examples
--------

See the examples for [`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-HkdfParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.HkdfParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

See also
--------

-   [`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HkdfParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HkdfParams</a>

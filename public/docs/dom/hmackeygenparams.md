HmacKeyGenParams
================

The `HmacKeyGenParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey), when generating a key for the [HMAC](subtlecrypto/sign#hmac) algorithm.

Properties
----------

`name`  
A [`DOMString`](domstring). This should be set to `HMAC`.

`hash`  
A [`DOMString`](domstring) representing the name of the [digest function](subtlecrypto/digest#supported_algorithms) to use. You can pass any of `SHA-1`, `SHA-256`, `SHA-384`, or `SHA-512` here.

 `length` <span class="badge inline optional">Optional</span>   
A `Number` — the length in bits of the key. If this is omitted, the length of the key is equal to the block size of the hash function you have chosen. Unless you have a good reason to use a different length, omit this property and use the default.

Examples
--------

See the examples for [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-HmacKeyGenParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.HmacKeyGenParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

See also
--------

-   [`SubtleCrypto.generateKey()`](subtlecrypto/generatekey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HmacKeyGenParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HmacKeyGenParams</a>

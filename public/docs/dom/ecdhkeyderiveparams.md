EcdhKeyDeriveParams
===================

The `EcdhKeyDeriveParams` dictionary of the [Web Crypto API](web_crypto_api) represents the object that should be passed as the `algorithm` parameter into [`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey), when using the [ECDH](subtlecrypto/derivekey#ecdh) algorithm.

ECDH enables two people who each have a key pair consisting of a public and a private key to derive a shared secret. They exchange public keys and use the combination of their private key and the other entity's public key to derive a secret key that they — and noone else — share.

The parameters for ECDH `deriveKey()` therefore include the other entity's public key, which is combined with this entity's private key to derive the shared secret.

Properties
----------

`name`  
A [`DOMString`](domstring). This should be set to `ECDH`.

`public`  
A [`CryptoKey`](cryptokey) object representing the public key of the other entity.

Examples
--------

See the examples for [`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-EcdhKeyDeriveParams">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto.EcdhKeyDeriveParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

See also
--------

-   [`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EcdhKeyDeriveParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EcdhKeyDeriveParams</a>

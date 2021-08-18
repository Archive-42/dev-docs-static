SubtleCrypto
============

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `SubtleCrypto` interface of the [Web Crypto API](web_crypto_api) provides a number of low-level cryptographic functions. Access to the features of `SubtleCrypto` is obtained through the [`subtle`](crypto/subtle) property of the [`Crypto`](crypto) object you get from [`Window.crypto`](window/crypto).

**Warning:** This API provides a number of low-level cryptographic primitives. It's very easy to misuse them, and the pitfalls involved can be very subtle.

Even assuming you use the basic cryptographic functions correctly, secure key management and overall security system design are extremely hard to get right, and are generally the domain of specialist security experts.

Errors in security system design and implementation can make the security of the system completely ineffective.

**If you're not sure you know what you are doing, you probably shouldn't be using this API.**

Properties
----------

*This interface doesn't inherit any properties, as it has no parent interface.*

Methods
-------

*This interface doesn't inherit any methods, as it has no parent interface.*

[`SubtleCrypto.encrypt()`](subtlecrypto/encrypt)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fufills with the encrypted data corresponding to the clear text, algorithm, and key given as parameters.

[`SubtleCrypto.decrypt()`](subtlecrypto/decrypt)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with the clear data corresponding to the encrypted text, algorithm, and key given as parameters.

[`SubtleCrypto.sign()`](subtlecrypto/sign)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with the signature corresponding to the text, algorithm, and key given as parameters.

[`SubtleCrypto.verify()`](subtlecrypto/verify)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating if the signature given as a parameter matches the text, algorithm, and key that are also given as parameters.

[`SubtleCrypto.digest()`](subtlecrypto/digest)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a digest generated from the algorithm and text given as parameters.

[`SubtleCrypto.generateKey()`](subtlecrypto/generatekey)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a newly-generated [`CryptoKey`](cryptokey), for symmetrical algorithms, or a [`CryptoKeyPair`](cryptokeypair), containing two newly generated keys, for asymmetrical algorithms. These will match the algorithm, usages, and extractability given as parameters.

[`SubtleCrypto.deriveKey()`](subtlecrypto/derivekey)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a newly generated [`CryptoKey`](cryptokey) derived from the master key and specific algorithm given as parameters.

[`SubtleCrypto.deriveBits()`](subtlecrypto/derivebits)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a newly generated buffer of pseudo-random bits derived from the master key and specific algorithm given as parameters.

[`SubtleCrypto.importKey()`](subtlecrypto/importkey)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a [`CryptoKey`](cryptokey) corresponding to the format, the algorithm, raw key data, usages, and extractability given as parameters.

[`SubtleCrypto.exportKey()`](subtlecrypto/exportkey)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a buffer containing the key in the requested format.

[`SubtleCrypto.wrapKey()`](subtlecrypto/wrapkey)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a wrapped symmetric key for usage (transfer and storage) in insecure environments. The wrapped key matches the format specified in the given parameters, and wrapping is done by the given wrapping key, using the specified algorithm.

[`SubtleCrypto.unwrapKey()`](subtlecrypto/unwrapkey)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that fulfills with a [`CryptoKey`](cryptokey) corresponding to the wrapped key given in the parameter.

Using SubtleCrypto
------------------

We can split the functions implemented by this API into two groups: cryptography functions and key management functions.

### Cryptography functions

These are the functions you can use to implement security features such as privacy and authentication in a system. The `SubtleCrypto` API provides the following cryptography functions:

\* [`sign()`](subtlecrypto/sign) and [`verify()`](subtlecrypto/verify): create and verify digital signatures.  
\* [`encrypt()`](subtlecrypto/encrypt) and [`decrypt()`](subtlecrypto/decrypt): encrypt and decrypt data.  
\* [`digest()`](subtlecrypto/digest): create a fixed-length, collision-resistant digest of some data.

### Key management functions

Except for [`digest()`](subtlecrypto/digest), all the cryptography functions in the API use cryptographic keys. In the `SubtleCrypto` API a cryptographic key is represented using a [`CryptoKey`](cryptokey) object. To perform operations like signing and encrypting, you pass a [`CryptoKey`](cryptokey) object into the [`sign()`](subtlecrypto/sign) or [`encrypt()`](subtlecrypto/encrypt) function.

#### Generating and deriving keys

The [`generateKey()`](subtlecrypto/generatekey) and [`deriveKey()`](subtlecrypto/derivekey) functions both create a new [`CryptoKey`](cryptokey) object.

The difference is that `generateKey()` will generate a new distinct key value each time you call it, while `deriveKey()` derives a key from some initial keying material. If you provide the same keying material to two separate calls to `deriveKey()`, you will get two `CryptoKey` objects that have the same underlying value. This is useful if, for example, you want to derive an encryption key from a password and later derive the same key from the same password to decrypt the data.

#### Importing and exporting keys

To make keys available outside your app, you need to export the key, and that's what [`exportKey()`](subtlecrypto/exportkey) is for. You can choose one of a number of export formats.

The inverse of `exportKey()` is [`importKey()`](subtlecrypto/importkey). You can import keys from other systems, and support for standard formats like [PKCS \#8](https://datatracker.ietf.org/doc/html/rfc5208) and [JSON Web Key](https://datatracker.ietf.org/doc/html/rfc7517) helps you do this. The `exportKey()` function exports the key in an unencrypted format.

If the key is sensitive you should use [`wrapKey()`](subtlecrypto/wrapkey), which exports the key and then encrypts it using another key; the API calls a "key-wrapping key".

The inverse of `wrapKey()` is [`unwrapKey()`](subtlecrypto/unwrapkey), which decrypts then imports the key.

#### Storing keys

`CryptoKey` objects can be stored using the [structured clone algorithm](web_workers_api/structured_clone_algorithm), meaning that you can store and retrieve them using standard web storage APIs. The specification expects that most developers will use the [IndexedDB API](indexeddb_api) to store `CryptoKey` objects.

### Supported algorithms

The cryptographic functions provided by the Web Crypto API can be performed by one or more different *cryptographic algorithms*: the `algorithm` argument to the function indicates which algorithm to use. Some algorithms need extra parameters: in these cases the `algorithm` argument is a dictionary object that includes the extra parameters.

The table below summarizes which algorithms are suitable for which cryptographic operations:

<table style="width:100%;"><colgroup><col style="width: 16%" /><col style="width: 16%" /><col style="width: 16%" /><col style="width: 16%" /><col style="width: 16%" /><col style="width: 16%" /></colgroup><thead><tr class="header"><th></th><th><p><a href="subtlecrypto/sign">sign()</a></p><p><a href="subtlecrypto/verify">verify()</a></p></th><th><p><a href="subtlecrypto/encrypt">encrypt()</a></p><p><a href="subtlecrypto/decrypt">decrypt()</a></p></th><th><a href="subtlecrypto/digest">digest()</a></th><th><p><a href="subtlecrypto/derivebits">deriveBits()</a></p><p><a href="subtlecrypto/derivekey">deriveKey()</a></p></th><th><p><a href="subtlecrypto/wrapkey">wrapKey()</a></p><p><a href="subtlecrypto/unwrapkey">unwrapKey()</a></p></th></tr></thead><tbody><tr class="odd"><td>RSASSA-PKCS1-v1_5</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr class="even"><td>RSA-PSS</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr class="odd"><td>ECDSA</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr class="even"><td>HMAC</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr class="odd"><td>RSA-OAEP</td><td></td><td>✓</td><td></td><td></td><td>✓</td></tr><tr class="even"><td>AES-CTR</td><td></td><td>✓</td><td></td><td></td><td>✓</td></tr><tr class="odd"><td>AES-CBC</td><td></td><td>✓</td><td></td><td></td><td>✓</td></tr><tr class="even"><td>AES-GCM</td><td></td><td>✓</td><td></td><td></td><td>✓</td></tr><tr class="odd"><td>SHA-1</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr class="even"><td>SHA-256</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr class="odd"><td>SHA-384</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr class="even"><td>SHA-512</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr class="odd"><td>ECDH</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr class="even"><td>HKDF</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr class="odd"><td>PBKDF2</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr class="even"><td>AES-KW</td><td></td><td></td><td></td><td></td><td>✓</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#subtlecrypto-interface">Web Cryptography API<br />
<span class="small">The definition of 'SubtleCrypto' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`SubtleCrypto`

37

12

34

11

24

10.1

7

37

37

34

24

10.3

7

6.0

`decrypt`

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

`deriveKey`

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

`generateKey`

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

`importKey`

37

12

\["Not supported: RSA-PSS, ECDSA, ECDH.", "Not supported: AES-CTR, HKDF, PBKDF2."\]

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

`secure_context_required`

60

79

75

No

47

No

60

60

No

47

No

8.0

`sign`

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

`unwrapKey`

37

12

Not supported: AES-CTR.

34

11

Returns `KeyOperation` instead of `Promise`

24

7

?

37

34

24

7

6.0

`verify`

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

`worker_support`

?

?

48

?

?

?

?

?

?

?

?

?

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

-   [Web Crypto API](web_crypto_api)
-   [Web security](https://developer.mozilla.org/en-US/docs/Web/Security)
-   [Privacy, permissions, and information security](https://developer.mozilla.org/en-US/docs/Web/Privacy)
-   [`Crypto`](crypto) and [`Crypto.subtle`](crypto/subtle).
-   [Crypto 101](https://www.crypto101.io/): an introductory course on cryptography.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto</a>

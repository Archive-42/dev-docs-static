Web Crypto API
==============

The **Web Crypto API** is an interface allowing a script to use cryptographic primitives in order to build systems using cryptography.

**Note:** This feature is available in [Web Workers](web_workers_api).

**Warning:** The Web Crypto API provides a number of low-level cryptographic primitives. It's very easy to misuse them, and the pitfalls involved can be very subtle.

Even assuming you use the basic cryptographic functions correctly, secure key management and overall security system design are extremely hard to get right, and are generally the domain of specialist security experts.

Errors in security system design and implementation can make the security of the system completely ineffective.

**If you're not sure you know what you are doing, you probably shouldn't be using this API.**

Interfaces
----------

Some browsers implemented an interface called [`Crypto`](crypto) without having it well defined or being cryptographically sound. In order to avoid confusion, methods and properties of this interface have been removed from browsers implementing the Web Crypto API, and all Web Crypto API methods are available on a new interface: [`SubtleCrypto`](subtlecrypto). The [`Crypto.subtle`](crypto/subtle) property gives access to an object implementing it.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/">Web Cryptography API</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Web_Crypto_API`

11

12

26

11

15

6.1

≤37

18

26

14

6.1

1.0

`getRandomValues`

11

12

26

11

15

6.1

≤37

18

26

14

6.1

1.0

`subtle`

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

3.0

BCD tables only load in the browser

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API</a>

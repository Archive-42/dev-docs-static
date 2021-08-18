Window.crypto
=============

The read-only `Window.crypto` property returns the [`Crypto`](../crypto) object associated to the global object. This object allows web pages access to certain cryptographic related services. Although the property itself is read-only, all of its methods (and the methods of its child object, [`SubtleCrypto`](../subtlecrypto)) are not read-only, and therefore vulnerable to attack by [polyfill](https://developer.mozilla.org/en-US/docs/Glossary/Polyfill).

Although `window.crypto` is available on all windows, the returned `Crypto` object only has one usable feature in insecure contexts: the [`getRandomValues()`](../crypto/getrandomvalues) method. In general, you should use this API only in secure contexts.

Syntax
------

    let cryptoObj = window.crypto || window.msCrypto; // for IE 11

### Value

An instance of the [`Crypto`](../crypto) interface, providing access to general-purpose cryptography and a strong random-number generator.

Example
-------

This example uses the [`Window.crypto`](crypto) property to access the [`getRandomValues()`](../crypto/getrandomvalues) method.

### JavaScript

    genRandomNumbers = function getRandomNumbers() {
      const array = new Uint32Array(10);
      window.crypto.getRandomValues(array);

      const randText = document.getElementById("myRandText");
      randText.textContent = "The random numbers are: "
      for (let i = 0; i < array.length; i++) {
        randText.textContent += array[i] + " ";
      }
    }

### HTML

    <p id="myRandText">The random numbers are: </p>
    <button type="button" onClick='genRandomNumbers()'>Generate 10 random numbers</button>

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-GlobalCrypto">Web Cryptography API<br />
<span class="small">The definition of 'Window.crypto' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`crypto`

37

12

1

11

24

6.1

37

37

4

24

6.1

3.0

See also
--------

-   The [`Window`](../window) global object
-   The [`Crypto`](../crypto) interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/crypto" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/crypto</a>

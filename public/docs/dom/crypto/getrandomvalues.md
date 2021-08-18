# Crypto.getRandomValues()

The `Crypto.getRandomValues()` method lets you get cryptographically strong random values. The array given as the parameter is filled with random numbers (random in its cryptographic meaning).

To guarantee enough performance, implementations are not using a truly random number generator, but they are using a pseudo-random number generator _seeded_ with a value with enough entropy. The pseudo-random number generator algorithm (PRNG) may vary across [user agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent), but is suitable for cryptographic purposes. Implementations are required to use a seed with enough entropy, like a system-level entropy source.

`getRandomValues()` is the only member of the `Crypto` interface which can be used from an insecure context.

## Syntax

    typedArray = cryptoObj.getRandomValues(typedArray);

### Parameters

`typedArray`  
An integer-based [`TypedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray), that is an [`Int8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int8Array), a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array), an [`Int16Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int16Array), a [`Uint16Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint16Array), an [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array), or a [`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array). All elements in the array are overwritten with random numbers.

### Return value

The same array passed as `typedArray` but with its contents replaced with the newly generated random numbers. Note that `typedArray` is modified in-place, and no copy is made.

### Exceptions

This method can throw an exception under error conditions.

[`DOMException`](../domexception) (name: [`QuotaExceededError`](../domexception#exception-quotaexceedederror))  
The requested length exceeds 65,536 bytes.

## Usage notes

Don't use `getRandomValues()` to generate encryption keys. Instead, use the [`generateKey()`](../subtlecrypto/generatekey) method. There are a few reasons for this; for example, `getRandomValues()` is not guaranteed to be running in a secure context.

There is no minimum degree of entropy mandated by the Web Cryptography specification. User agents are instead urged to provide the best entropy they can when generating random numbers, using a well-defined, efficient pseudorandom number generator built into the user agent itself, but seeded with values taken from an external source of pseudorandom numbers, such as a platform-specific random number function, the Unix `/dev/urandom` device, or other source of random or pseudorandom data.

## Examples

    /* Assuming that window.crypto.getRandomValues is available */

    var array = new Uint32Array(10);
    window.crypto.getRandomValues(array);

    console.log("Your lucky numbers:");
    for (var i = 0; i < array.length; i++) {
      console.log(array[i]);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#Crypto-method-getRandomValues">Web Cryptography API</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

## See also

- [Web Crypto API](../web_crypto_api)
- [`Window.crypto`](../window/crypto) to get a [`Crypto`](../crypto) object.
- [`Math.random`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random), a non-cryptographic source of random numbers.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Crypto/getRandomValues" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Crypto/getRandomValues</a>

# Crypto.subtle

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Crypto.subtle` read-only property returns a [`SubtleCrypto`](../subtlecrypto) which can then be used to perform low-level cryptographic operations.

## Syntax

    var crypto = crypto.subtle;

### Value

A [`SubtleCrypto`](../subtlecrypto) object you can use to interact with the Web Crypto API's low-level cryptography features.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/WebCryptoAPI/#dfn-Crypto">Web Cryptography API<br />
<span class="small">The definition of 'Crypto.subtle' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [`Crypto`](../crypto).
- [`SubtleCrypto`](../subtlecrypto).
- [Compatibility test page](https://vibornoff.github.io/webcrypto-examples/index.html).
- [Shim for IE11 and Safari](https://github.com/vibornoff/webcrypto-shim).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Crypto/subtle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Crypto/subtle</a>

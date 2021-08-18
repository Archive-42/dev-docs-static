WindowOrWorkerGlobalScope.btoa()
================================

The `WindowOrWorkerGlobalScope.btoa()` method creates a [Base64](https://developer.mozilla.org/en-US/docs/Glossary/Base64)-encoded ASCII string from a [binary string](../domstring/binary) (i.e., a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) object in which each character in the string is treated as a byte of binary data).

You can use this method to encode data which may otherwise cause communication problems, transmit it, then use the [`atob()`](atob) method to decode the data again. For example, you can encode control characters such as ASCII values 0 through 31.

Syntax
------

    var encodedData = scope.btoa(stringToEncode);

### Parameters

`stringToEncode`  
The [binary string](../domstring/binary) to encode.

### Return value

An ASCII string containing the Base64 representation of `stringToEncode`.

### Exceptions

`InvalidCharacterError`  
The string contained a character that did not fit in a single byte. See "Unicode strings" below for more detail.

Example
-------

    const encodedData = window.btoa('Hello, world'); // encode a string
    const decodedData = window.atob(encodedData); // decode the string

Unicode strings
---------------

The `btoa()` function takes a JavaScript string as a parameter. In JavaScript strings are represented using the UTF-16 character encoding: in this encoding, strings are represented as a sequence of 16-bit (2 byte) units. Every ASCII character fits into the first byte of one of these units, but many other characters don't.

Base64, by design, expects binary data as its input. In terms of JavaScript strings, this means strings in which each character occupies only one byte. So if you pass a string into `btoa()` containing characters that occupy more than one byte, you will get an error, because this is not considered binary data:

    const ok = "a";
    console.log(ok.codePointAt(0).toString(16)); //   61: occupies < 1 byte

    const notOK = "✓"
    console.log(notOK.codePointAt(0).toString(16)); // 2713: occupies > 1 byte

    console.log(btoa(ok));    // YQ==
    console.log(btoa(notOK)); // error

If you need to encode Unicode text as ASCII using `btoa()`, one option is to convert the string such that each 16-bit unit occupies only one byte. For example:

    // convert a Unicode string to a string in which
    // each 16-bit unit occupies only one byte
    function toBinary(string) {
      const codeUnits = new Uint16Array(string.length);
      for (let i = 0; i < codeUnits.length; i++) {
        codeUnits[i] = string.charCodeAt(i);
      }
      return String.fromCharCode(...new Uint8Array(codeUnits.buffer));
    }

    // a string that contains characters occupying > 1 byte
    const myString = "☸☹☺☻☼☾☿";

    const converted = toBinary(myString);
    const encoded = btoa(converted);
    console.log(encoded);                 // OCY5JjomOyY8Jj4mPyY=

If you do this, of course you'll have to reverse the conversion on the decoded string:

    function fromBinary(binary) {
      const bytes = new Uint8Array(binary.length);
      for (let i = 0; i < bytes.length; i++) {
        bytes[i] = binary.charCodeAt(i);
      }
      return String.fromCharCode(...new Uint16Array(bytes.buffer));
    }

    const decoded = atob(encoded);
    const original = fromBinary(decoded);
    console.log(original);                // ☸☹☺☻☼☾☿

Polyfill
--------

You can use a polyfill from <https://github.com/MaxArt2501/base64-js/blob/master/base64.js> for browsers that don't support it.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-btoa">HTML Living Standard<br />
<span class="small">The definition of 'WindowOrWorkerGlobalScope.btoa()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Method moved to the <code>WindowOrWorkerGlobalScope</code> mixin in the latest spec.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/#dom-windowbase64-btoa">HTML 5.1<br />
<span class="small">The definition of 'WindowBase64.btoa()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>. No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#dom-windowbase64-btoa">HTML5<br />
<span class="small">The definition of 'WindowBase64.btoa()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>. Creation of <code>WindowBase64</code> (properties where on the target before it).</td></tr></tbody></table>

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

`btoa`

4

12

1

10

10.5

3

≤37

18

4

11

1

1.0

See also
--------

-   [`data` URIs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs)
-   [`atob()`](atob)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/btoa</a>

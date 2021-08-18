WindowOrWorkerGlobalScope.atob()
================================

The `WindowOrWorkerGlobalScope.atob()` function decodes a string of data which has been encoded using [Base64](https://developer.mozilla.org/en-US/docs/Glossary/Base64) encoding. You can use the [`btoa()`](btoa) method to encode and transmit data which may otherwise cause communication problems, then transmit it and use the `atob()` method to decode the data again. For example, you can encode, transmit, and decode control characters such as ASCII values 0 through 31.

For use with Unicode or UTF-8 strings, see the note on "Unicode strings" in the page for [`btoa()`](btoa).

Syntax
------

    var decodedData = scope.atob(encodedData);

### Parameters

`encodedData`  
A [binary string](../domstring/binary) contains an base64 encoded data.

### Return value

An ASCII string containing decoded data from `encodedData`.

### Exceptions

 [`DOMException`](../domexception) (name: `InvalidCharacterError`)  
Throws if `encodedData` is not valid base64.

Example
-------

    const encodedData = window.btoa('Hello, world'); // encode a string
    const decodedData = window.atob(encodedData); // decode the string

Polyfill
--------

You can use a polifill from <https://github.com/MaxArt2501/base64-js/blob/master/base64.js> for browsers that don't support it.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-atob">HTML Living Standard<br />
<span class="small">The definition of 'WindowOrWorkerGlobalScope.atob()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Method moved to the <code>WindowOrWorkerGlobalScope</code> mixin in the latest spec.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/#dom-windowbase64-atob">HTML 5.1<br />
<span class="small">The definition of 'WindowBase64.atob()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>. No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#dom-windowbase64-atob">HTML5<br />
<span class="small">The definition of 'WindowBase64.atob()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>. Creation of <code>WindowBase64</code> (properties where on the target before it).</td></tr></tbody></table>

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

`atob`

4

12

1

27

`atob()` ignores all space characters in the argument to comply with the latest HTML5 spec (see [bug 711180](https://bugzil.la/711180)).

10

10.5

3

≤37

18

4

27

`atob()` ignores all space characters in the argument to comply with the latest HTML5 spec (see [bug 711180](https://bugzil.la/711180)).

11

1

1.0

See also
--------

-   [`data` URIs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs)
-   [`btoa()`](btoa)
-   [Components.utils.importGlobalProperties](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XPCOM/Language_Bindings/Components.utils.importGlobalProperties)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/atob</a>

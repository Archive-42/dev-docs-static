USVString
=========

A `USVString` is a sequence of [Unicode scalar values](https://www.unicode.org/glossary/#unicode_scalar_value). This definition differs from that of [`DOMString`](domstring) or the JavaScript [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) type in that it always represents a valid sequence suitable for text processing, while the latter can contain surrogate code points. The `USVString` type is generally found in APIs that perform text processing, while [`DOMString`](domstring) is used by most other APIs.

When a `USVString` is provided to JavaScript, it maps to the JavaScript primitive [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) with the UTF-16 encoding of its sequence of Unicode scalar values.

When a Web API accepts a `USVString`, the JavaScript value provided is first stringified, in the same way as for [`DOMString`](domstring). The resulting string is then further converted to `USVString` by replacing any surrogate code points (or equivalently, any unpaired surrogate code units) with the Unicode "replacement character" U+FFFD (�).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://heycam.github.io/webidl/#idl-USVString">Web IDL<br />
<span class="small">The definition of 'USVString' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition of the <code>USVString</code> type itself.</td></tr><tr class="even"><td><a href="https://heycam.github.io/webidl/#es-USVString">Web IDL</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>This defines how JavaScript values are converted to <code>USVString</code> and vice versa.</td></tr></tbody></table>

See also
--------

-   [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
-   [`DOMString`](domstring)
-   [`CSSOMString`](cssomstring)
-   [Binary strings](domstring/binary)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/USVString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/USVString</a>

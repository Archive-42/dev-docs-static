# DOMString

A `DOMString` is a sequence of 16-bit unsigned integers, typically interpreted as UTF-16 [code units](https://www.unicode.org/glossary/#code_unit). This corresponds exactly to the JavaScript [primitive String type](https://tc39.es/ecma262/#sec-ecmascript-language-types-string-type). When a `DOMString` is provided to JavaScript, it maps directly to the corresponding [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

When a Web API accepts a `DOMString`, the value provided will be stringified, using the `ToString` abstract operation. (For types other than Symbol, this has the same behavior as the [`String()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/String) function.)

Certain Web APIs accepting a `DOMString` have an additional legacy behavior, where passing [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) stringifies to the empty string instead of the usual `"null"`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://heycam.github.io/webidl/#idl-DOMString">Web IDL<br />
<span class="small">The definition of 'DOMString' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://heycam.github.io/webidl/#es-DOMString">Web IDL</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>This defines how JavaScript values are converted to <code>DOMString</code> and vice versa.</td></tr></tbody></table>

## See also

- JavaScript [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- [`USVString`](usvstring)
- [`CSSOMString`](cssomstring)
- [Binary strings](domstring/binary)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMString</a>

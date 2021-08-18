# CSSOMString

`CSSOMString` is used to denote string data in [CSSOM](css_object_model) specifications and can refer to either [`DOMString`](domstring) or [`USVString`](usvstring). When a specification says `CSSOMString`, it depends on the browser vendors to choose whether to use `DOMString` or `USVString`. While browser implementations that use UTF-8 internally to represent strings in memory can use `USVString` when the specification says `CSSOMString`, implementations that already represent strings as 16-bit sequences might choose to use `DOMString` instead.

#### Implementation differences

<table><thead><tr class="header"><th>Browser</th><th>DOMString or USVString for CSSOMString</th></tr></thead><tbody><tr class="odd"><td>Firefox (Gecko)</td><td>USVString</td></tr><tr class="even"><td>Chrome (Blink)</td><td>USVString</td></tr><tr class="odd"><td>Safari (WebKit)</td><td>USVString</td></tr><tr class="even"><td>Edge (EdgeHTML)</td><td>-</td></tr><tr class="odd"><td>Opera (Blink)</td><td>USVString</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#cssomstring-type">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSOMString' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- [`CSS_Object_Model`](css_object_model)
- [`DOMString`](domstring)
- [`USVString`](usvstring)
- [Binary strings](domstring/binary)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSOMString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSOMString</a>

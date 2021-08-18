TextDecoder.prototype.encoding
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `TextDecoder.prototype.encoding` read-only property returns a [`DOMString`](../domstring) containing the name of the decoding algorithm used by the specific decoder.

It can be one of the following values:

-   The recommended encoding for the Web: `'utf-8'`.
-   The legacy single-byte encodings: `'ibm866'`, `'iso-8859-2'`, `'iso-8859-3'`, `'iso-8859-4'`, `'iso-8859-5'`, `'iso-8859-6'`, `'iso-8859-7'`, `'iso-8859-8''`, `'iso-8859-8i'`, `'iso-8859-10'`, `'iso-8859-13'`, `'iso-8859-14'`, `'iso-8859-15'`, `'iso-8859-16'`, `'koi8-r'`, `'koi8-u'`, `'macintosh'`, `'windows-874'`, `'windows-1250'`, `'windows-1251'`, `'windows-1252'`, `'windows-1253'`, `'windows-1254'`, `'windows-1255'`, `'windows-1256'`, `'windows-1257'`, `'windows-1258'`, or `'x-mac-cyrillic'`.
-   The legacy multi-byte Chinese (simplified) encodings: `'gbk'`, `'gb18030'`, and `'hz-gb-2312'`.
-   The legacy multi-byte Chinese (traditional) encoding: `'big5'`.
-   The legacy multi-byte Japanese encodings: `'euc-jp'`, `'iso-2022-jp'`, and `'shift-jis'`.
-   The legacy multi-byte Korean encodings: `'euc-kr'`, and `'iso-2022-kr'`.
-   The legacy miscellaneous encodings: `'utf-16be'`, `'utf-16le'`, and `'x-user-defined'`.
-   A special encoding, `'replacement'`, which only emits an error and an `EOF` code point. It is used to prevent attacks that mismatch encodings between the client and server. It can happen with `ISO-2022-CN` and `ISO-2022-CN-ext`.

Syntax
------

    var b = decoder.decoding;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://encoding.spec.whatwg.org/#dom-textdecoder-encoding">Encoding<br />
<span class="small">The definition of 'TextDecoder.encoding' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`encoding`

38

≤79

19

18

Implemented a slightly different version of the spec.

No

25

10.1

38

38

19

18

Implemented a slightly different version of the spec.

Yes

10.3

3.0

See also
--------

-   The [`TextDecoder`](../textdecoder) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder/encoding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextDecoder/encoding</a>

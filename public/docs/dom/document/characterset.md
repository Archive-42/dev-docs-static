# Document.characterSet

The `Document.characterSet` read-only property returns the [character encoding](https://developer.mozilla.org/en-US/docs/Glossary/character_encoding) of the document that it's currently rendered with. (A character encoding is a set of characters _and_ how to interpret bytes into those characters.)

A “character set” and a “character encoding” are related, but different. Despite the name of this property, it returns the _encoding_.

Users can override the developer-specified encoding inside the [Content-Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) header or inline like `<meta charset="utf-8">`, such as with Firefox's View → Text Encoding menu. This override is provided to fix incorrect developer-specified encodings that result in [garbled text](https://en.wikipedia.org/wiki/Mojibake).

The properties `document.charset` and `document.inputEncoding` are legacy aliases for `document.characterSet`. Do not use them any more.

## Syntax

    var string = document.characterSet;

## Examples

    <button onclick="console.log(document.characterSet);">
      Log character encoding
    </button>
    <!-- displays document's character encoding in the dev console, such as "ISO-8859-1" or "UTF-8" -->

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-characterset">DOM<br />
<span class="small">The definition of 'characterSet' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`characterSet`

1

1

`charset` alias was made read-only in Chrome 45.

1

12

12

12

1

44

1.5

9

4

9

≤12.1

No

No

3

3

3

1

1

`charset` alias was made read-only in WebView 45.

1

18

18

`charset` alias was made read-only in Chrome 45.

18

4

44

4

Yes

No

No

1

1

1

1.0

1.0

`charset` alias was made read-only in Samsung Internet 5.0.

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/characterSet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/characterSet</a>

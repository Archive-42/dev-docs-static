# DOMParser.parseFromString()

The `parseFromString()` method of the [`DOMParser`](../domparser) interface parses a string containing either HTML or XML, returning an [`HTMLDocument`](../htmldocument) or an [`XMLDocument`](../xmldocument).

## Syntax

    const doc = domparser.parseFromString(string, mimeType)

### Parameters

`string`  
The [`DOMString`](../domstring) to be parsed. It must contain either an [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML), [xml](https://developer.mozilla.org/en-US/docs/Glossary/XML), <span class="page-not-created">xhtml+xml</span>, or [svg](https://developer.mozilla.org/en-US/docs/Glossary/SVG) document.

`mimeType`  
A [`DOMString`](../domstring). This string determines whether the XML parser or the HTML parser is used to parse the string. Valid values are:

- `text/html`
- `text/xml`
- `application/xml`
- `application/xhtml+xml`
- `image/svg+xml`

A value of `text/html` will invoke the HTML parser, and the method will return an [`HTMLDocument`](../htmldocument). Any other valid value will invoke the XML parser, and the method will return an [`XMLDocument`](../xmldocument).

Any other value will cause a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) to be thrown.

### Return value

An [`HTMLDocument`](../htmldocument) or an [`XMLDocument`](../xmldocument), depending on the `mimeType` argument.

## Examples

### Parsing XML, SVG, and HTML

This example shows how to parse XML, SVG, and HTML. Note that a MIME type of `text/html` will invoke the HTML parser, and any other valid MIME type will invoke the XML parser.

    const parser = new DOMParser();

    const xmlString = "<warning>Beware of the tiger</warning>";
    const doc1 = parser.parseFromString(xmlString, "application/xml");
    // XMLDocument

    const svgString = "<circle cx=\"50\" cy=\"50\" r=\"50\"/>";
    const doc2 = parser.parseFromString(svgString, "image/svg+xml");
    // XMLDocument

    const htmlString = "<strong>Beware of the leopard</strong>";
    const doc3 = parser.parseFromString(htmlString, "text/html");
    // HTMLDocument

    console.log(doc1.documentElement.textContent)
    // "Beware of the tiger"

    console.log(doc2.firstChild.tagName);
    // "circle"

    console.log(doc3.body.firstChild.textContent);
    // "Beware of the leopard"

### Error handling

Note that if the XML parser is used and parsing fails, the `DOMParser` does not throw an exception, but instead returns an error document:

    const parser = new DOMParser();

    const xmlString = "<warning>Beware of the missing closing tag";
    const doc = parser.parseFromString(xmlString, "application/xml");

    console.log(doc.documentElement.tagName);
    // parsererror

    console.log(doc.documentElement.textContent);
    // XML Parsing Error: no element found

The parsing error may also be reported to the browser's JavaScript console.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-domparser-parsefromstring">HTML Living Standard<br />
<span class="small">The definition of 'parseFromString()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`parseFromString`

1

12

1

9

8

3.2

1

Yes

4

Yes

Yes

Yes

`html`

31

12

12

10

17

9.1

≤37

31

14

?

9.3

3.0

`svg`

4

12

10

10

15

3.2

≤37

18

10

Yes

?

1.0

`xml`

1

12

1

9

8

3.2

1

18

Yes

Yes

?

1.0

## See also

- [`XMLSerializer`](../xmlserializer)
- [`JSON.parse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) - counterpart for [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) documents.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMParser/parseFromString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMParser/parseFromString</a>

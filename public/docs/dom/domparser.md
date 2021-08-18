# DOMParser

The `DOMParser` interface provides the ability to parse [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML) or [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) source code from a string into a DOM [`Document`](document).

You can perform the opposite operation—converting a DOM tree into XML or HTML source—using the [`XMLSerializer`](xmlserializer) interface.

In the case of an HTML document, you can also replace portions of the DOM with new DOM trees built from HTML by setting the value of the [`Element.innerHTML`](element/innerhtml) and [`outerHTML`](element/outerhtml) properties. These properties can also be read to fetch HTML fragments corresponding to the corresponding DOM subtree.

Note that [`XMLHttpRequest`](xmlhttprequest) can parse XML and HTML directly from a URL-addressable resource, returning a `Document` in its [`response`](xmlhttprequest/response) property.

## Constructor

[`DOMParser()`](domparser/domparser)  
Creates a new `DOMParser` object.

## Methods

[`DOMParser.parseFromString()`](domparser/parsefromstring)  
Parses a string using either the HTML parser or the XML parser, returning an [`HTMLDocument`](htmldocument) or [`XMLDocument`](xmldocument).

## Examples

### Parsing XML, SVG, and HTML

This example shows how to parse XML, SVG, and HTML. Note that a MIME type of `text/html` will invoke the HTML parser, and any of the other MIME types that are accepted by this method will invoke the XML parser.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-parsing-and-serialization">HTML Living Standard<br />
<span class="small">The definition of 'DOM parsing' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`DOMParser`

1

12

1

9

8

3.2

1

18

4

10.1

2

1.0

`DOMParser`

1

12

1

9

8

3.2

1

18

4

Yes

2

1.0

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

## See also

- [Parsing and serializing XML](https://developer.mozilla.org/en-US/docs/Web/Guide/Parsing_and_serializing_XML)
- [`XMLHttpRequest`](xmlhttprequest)
- [`XMLSerializer`](xmlserializer)
- [`JSON.parse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) - counterpart for [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) documents.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMParser" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMParser</a>

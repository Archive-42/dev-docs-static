# Document.body

The `Document.body` property represents the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) or [`<frameset>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frameset) node of the current document, or `null` if no such element exists.

## Syntax

    const objRef = document.body
    document.body = objRef

## Example

    // Given this HTML: <body id="oldBodyElement"></body>
    alert(document.body.id); // "oldBodyElement"

    const aNewBodyElement = document.createElement("body");

    aNewBodyElement.id = "newBodyElement";
    document.body = aNewBodyElement;
    alert(document.body.id); // "newBodyElement"

## Notes

`document.body` is the element that contains the content for the document. In documents with `<body>` contents, returns the `<body>` element, and in frameset documents, this returns the outermost `<frameset>` element.

Though the `body` property is settable, setting a new body on a document will effectively remove all the current children of the existing `<body>` element.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#dom-document-body">HTML Living Standard<br />
<span class="small">The definition of 'Document.body' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/dom.html#dom-document-body">HTML 5.1<br />
<span class="small">The definition of 'Document.body' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/dom.html#dom-document-body">HTML5<br />
<span class="small">The definition of 'Document.body' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`body`

1

12

1

The `body` property was implemented on the `HTMLDocument` interface in Firefox for a long time, hence `document.body` would not return the `<body>` element if the document's `Content-Type` was not set to `text/html` or `application/xhtml+xml` (or if it came from `DOMParser.parseFromString` without the `text/html` type being used). This has been fixed in Firefox 60.

4

9.6

1

1

18

4

The `body` property was implemented on the `HTMLDocument` interface in Firefox for a long time, hence `document.body` would not return the `<body>` element if the document's `Content-Type` was not set to `text/html` or `application/xhtml+xml` (or if it came from `DOMParser.parseFromString` without the `text/html` type being used). This has been fixed in Firefox 60.

10.1

1

1.0

## See also

- [`document.head`](head)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/body" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/body</a>

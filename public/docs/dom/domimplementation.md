# DOMImplementation

The `DOMImplementation` interface represents an object providing methods which are not dependent on any particular document. Such an object is returned by the [`Document.implementation`](document/implementation) property.

## Property

_This interface has no specific property and doesn't inherit any._

## Methods

_No inherited method._

[`DOMImplementation.createDocument()`](domimplementation/createdocument)  
Creates and returns an [`XMLDocument`](xmldocument).

[`DOMImplementation.createDocumentType()`](domimplementation/createdocumenttype)  
Creates and returns a [`DocumentType`](documenttype).

[`DOMImplementation.createHTMLDocument()`](domimplementation/createhtmldocument)  
Creates and returns an HTML [`Document`](document).

[`DOMImplementation.hasFeature()`](domimplementation/hasfeature)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if a given feature is supported or not. This function is unreliable and kept for compatibility purpose alone: except for SVG-related queries, it always returns `true`. Old browsers are very inconsistent in their behavior.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#domimplementation">DOM<br />
<span class="small">The definition of 'DOMImplementation' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Removed the <code>getFeature()</code> method.<br />
Added the <code>createHTMLDocument()</code> method.<br />
Modified the return type of <code>createDocument()</code> from <a href="document"><code>Document</code></a> to <a href="xmldocument"><code>XMLDocument</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-102161490">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'DOMImplementation' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the <code>getFeature()</code> method (never implemented by any user agent).</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-102161490">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'DOMImplementation' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the <code>createDocument()</code> and <code>createDocumentType()</code> methods.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-102161490">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'DOMImplementation' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`DOMImplementation`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`createDocument`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`createDocumentType`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`createHTMLDocument`

1

12

4

9

The `title` parameter is required, but can be empty string.

≤12.1

1

1

18

4

≤12.1

1

1.0

`hasFeature`

1

12

1

Since Firefox 19, `hasFeature()` mostly returns `true`.

6

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [The DOM interfaces index.](document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation</a>

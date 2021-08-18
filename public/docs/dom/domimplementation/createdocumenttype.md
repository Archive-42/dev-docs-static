# DOMImplementation.createDocumentType()

The `DOMImplementation.createDocumentType()` method returns a [`DocumentType`](../documenttype) object which can either be used with [`DOMImplementation.createDocument`](createdocument) upon document creation or can be put into the document via methods like [`Node.insertBefore()`](../node/insertbefore) or [`Node.replaceChild()`](../node/replacechild).

## Syntax

    var doctype = document.implementation.createDocumentType(qualifiedNameStr, publicId, systemId);

### Parameters

`qualifiedNameStr`  
Is a [`DOMString`](../domstring) containing the qualified name, like `svg:svg`.

`publicId`  
Is a [`DOMString`](../domstring) containing the `PUBLIC` identifier.

`systemId`  
Is a [`DOMString`](../domstring) containing the `SYSTEM` identifiers.

## Example

    var dt = document.implementation.createDocumentType('svg:svg', '-//W3C//DTD SVG 1.1//EN', 'http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd');
    var d = document.implementation.createDocument('http://www.w3.org/2000/svg', 'svg:svg', dt);
    alert(d.doctype.publicId); // -//W3C//DTD SVG 1.1//EN

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domimplementation-createdocumenttype">DOM<br />
<span class="small">The definition of 'DOMImplementation.createDocumentType' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-3-Core/">Document Object Model (DOM) Level 3 Core Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#Level-2-Core-DOM-createDocType">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'DOMImplementation.createDocumentType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#Level-2-Core-DOM-createDocType">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'DOMImplementation.createDocumentType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- The [`DOMImplementation`](../domimplementation) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation/createDocumentType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation/createDocumentType</a>

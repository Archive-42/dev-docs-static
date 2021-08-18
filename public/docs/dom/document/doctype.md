# Document.doctype

Returns the Document Type Declaration (DTD) associated with current document. The returned object implements the [`DocumentType`](../documenttype) interface. Use [`DOMImplementation.createDocumentType()`](../domimplementation/createdocumenttype) to create a `DocumentType`.

## Syntax

    doctype = document.doctype;

- `doctype` is a read-only property.

## Example

    var doctypeObj = document.doctype;

    console.log(
      "doctypeObj.name: "           + doctypeObj.name            + "\n" +
      "doctypeObj.internalSubset: " + doctypeObj.internalSubset  + "\n" +
      "doctypeObj.publicId: "       + doctypeObj.publicId        + "\n" +
      "doctypeObj.systemId: "       + doctypeObj.systemId
    );

## Notes

The property returns `null` if there is no DTD associated with the current document.

DOM level 2 doesn't support editing the document type declaration.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-doctype">DOM<br />
<span class="small">The definition of 'Document: doctype' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`doctype`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/doctype" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/doctype</a>

# DOMImplementation.createDocument()

The `DOMImplementation.createDocument()` method creates and returns an [`XMLDocument`](../xmldocument).

## Syntax

    var doc = document.implementation.createDocument(namespaceURI, qualifiedNameStr, documentType);

### Parameters

`namespaceURI`  
Is a [`DOMString`](../domstring) containing the namespace URI of the document to be created, or `null` if the document doesn't belong to one.

`qualifiedNameStr`  
Is a [`DOMString`](../domstring) containing the qualified name, that is an optional prefix and colon plus the local root element name, of the document to be created.

`documentType` <span class="badge inline optional">Optional</span>  
Is the [`DocumentType`](../documenttype) of the document to be created. It defaults to `null`.

## Example

    var doc = document.implementation.createDocument ('http://www.w3.org/1999/xhtml', 'html', null);
    var body = document.createElementNS('http://www.w3.org/1999/xhtml', 'body');
    body.setAttribute('id', 'abc');
    doc.documentElement.appendChild(body);
    alert(doc.getElementById('abc')); // [object HTMLBodyElement]

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domimplementation-createdocument">DOM<br />
<span class="small">The definition of 'DOMImplementation.createDocument' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Modified the return type of <code>createDocument()</code> from <a href="../document"><code>Document</code></a> to <a href="../xmldocument"><code>XMLDocument</code></a>.<br />
The third argument of <code>createDocument()</code>, <em>doctype</em>, is now optional and default to <code>null</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#Level-2-Core-DOM-createDocument">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'DOMImplementation.createDocument' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#Level-2-Core-DOM-createDocument">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'DOMImplementation.createDocument' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- The [`DOMImplementation`](../domimplementation) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation/createDocument" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation/createDocument</a>

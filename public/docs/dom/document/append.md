# Document.append()

The `Document.append()` method inserts a set of [`Node`](../node) objects or [`DOMString`](../domstring) objects after the last child of the document. [`DOMString`](../domstring) objects are inserted as equivalent [`Text`](../text) nodes.

This method appends a child to a `Document`. To append to an arbitrary element in the tree, see [`Element.append()`](../element/append).

## Syntax

    append(...nodesOrDOMStrings)

### Parameters

`nodesOrDOMStrings`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to insert.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Appending a root element to a document

If you try to append an element to an existing HTML document, it might throw a <span class="page-not-created">`HierarchyRequestError`</span> given a [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element already exists.

    let html = document.createElement("html");
    document.append(html);
    // HierarchyRequestError: The operation would yield an incorrect node tree.

If you are creating a new document without any existing element, you can append a root HTML element (or a root SVG element):

    let doc = new Document();
    let html = document.createElement("html");
    doc.append(html);

    doc.children; // HTMLCollection [<html>]

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-append">DOM<br />
<span class="small">The definition of 'ParentNode.append()' in that specification.</span></a></td></tr></tbody></table>

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

`append`

54

17

49

No

41

10

54

54

49

41

10

6.0

## See also

- [`Document.prepend()`](prepend)
- [`Element.append()`](../element/append)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/append" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/append</a>

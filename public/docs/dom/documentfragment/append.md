# DocumentFragment.append()

The `DocumentFragment.append()` method inserts a set of [`Node`](../node) objects or [`DOMString`](../domstring) objects after the last child of the document fragment. [`DOMString`](../domstring) objects are inserted as equivalent [`Text`](../text) nodes.

This method appends a child to a `DocumentFragment`. To append to an arbitrary element in the tree, see [`Element.append()`](../element/append).

## Syntax

    append(...nodesOrDOMStrings)

### Parameters

`nodesOrDOMStrings`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to insert.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Appending an element to a document fragment

    let fragment = new DocumentFragment();
    let div = document.createElement("div");
    fragment.append(div);

    fragment.children; // HTMLCollection [<div>]

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

- [`DocumentFragment.prepend()`](prepend)
- [`Element.append()`](../element/append)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/append" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/append</a>

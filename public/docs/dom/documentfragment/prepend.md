# DocumentFragment.prepend()

The `DocumentFragment.prepend()` method inserts a set of [`Node`](../node) objects or [`DOMString`](../domstring) objects before the first child of the document fragment. [`DOMString`](../domstring) objects are inserted as equivalent [`Text`](../text) nodes.

This method prepends a child to a `DocumentFragment`. To prepend to an arbitrary element in the tree, see [`Element.prepend()`](../element/prepend).

## Syntax

    prepend(...nodesOrDOMStrings)

### Parameters

`nodesOrDOMStrings`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to insert.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Prepending an element to a document fragment

    let fragment = new DocumentFragment();
    let div = document.createElement("div");
    let p = document.createElement("p");
    fragment.append(p);
    fragment.prepend(div);

    fragment.children; // HTMLCollection [<div>, <p>]

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-prepend">DOM<br />
<span class="small">The definition of 'ParentNode.prepend()' in that specification.</span></a></td></tr></tbody></table>

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

`prepend`

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

- [`DocumentFragment.append()`](append)
- [`Element.prepend()`](../element/prepend)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/prepend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/prepend</a>

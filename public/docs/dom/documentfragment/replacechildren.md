# DocumentFragment.replaceChildren()

The `DocumentFragment.replaceChildren()` method replaces the existing children of a `DocumentFragment` with a specified new set of children. These can be [`DOMString`](../domstring) or [`Node`](../node) objects.

## Syntax

    replaceChildren(...nodesOrDOMStrings)

### Parameters

`nodesOrDOMStrings`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to replace the `DocumentFragment`'s existing children with. If no replacement objects are specified, then the `DocumentFragment` is emptied of all child nodes.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: The [constraints of the node tree](https://dom.spec.whatwg.org/#concept-node-tree) are violated.

## Examples

### Emptying a document fragment

`replaceChildren()` provides a very convenient mechanism for emptying a document fragment of all its children. You call it on the document fragment without any argument specified:

    let fragment = new DocumentFragment();
    let div = document.createElement("div");
    let p = document.createElement("p");
    fragment.append(p);
    fragment.prepend(div);

    fragment.children; // HTMLCollection [<div>, <p>]

    fragment.replaceChildren();

    fragment.children; // HTMLCollection []

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-replacechildren">DOM<br />
<span class="small">The definition of 'ParentNode.replaceChildren()' in that specification.</span></a></td></tr></tbody></table>

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

`replaceChildren`

86

86

78

No

72

14

86

86

79

61

14

14.0

## See also

- [`DocumentFragment.prepend()`](prepend)
- [`DocumentFragment.append()`](append)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/replaceChildren" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment/replaceChildren</a>

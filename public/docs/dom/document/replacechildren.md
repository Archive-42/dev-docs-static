# Document.replaceChildren()

The `Document.replaceChildren()` method replaces the existing children of a `Document` with a specified new set of children.

## Syntax

    replaceChildren(...nodesOrDOMStrings)

### Parameters

`nodesOrDOMStrings`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to replace the `Document`'s existing children with. If no replacement objects are specified, then the `Document` is emptied of all child nodes.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: The [constraints of the node tree](https://dom.spec.whatwg.org/#concept-node-tree) are violated.

## Examples

### Emptying a document

`replaceChildren()` provides a very convenient mechanism for emptying a document of all its children. You call it on the document without any argument specified:

    document.replaceChildren();
    document.children; // HTMLCollection []

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

- [`Document.prepend()`](prepend)
- [`Document.append()`](append)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/replaceChildren" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/replaceChildren</a>

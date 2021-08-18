# Element.append()

The `Element.append()` method inserts a set of [`Node`](../node) objects or [`DOMString`](../domstring) objects after the last child of the `Element`. [`DOMString`](../domstring) objects are inserted as equivalent [`Text`](../text) nodes.

Differences from [`Node.appendChild()`](../node/appendchild):

- `Element.append()` allows you to also append [`DOMString`](../domstring) objects, whereas `Node.appendChild()` only accepts [`Node`](../node) objects.
- `Element.append()` has no return value, whereas `Node.appendChild()` returns the appended [`Node`](../node) object.
- `Element.append()` can append several nodes and strings, whereas `Node.appendChild()` can only append one node.

## Syntax

    append(...nodesOrDOMStrings)

### Parameters

`nodesOrDOMStrings`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to insert.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Appending an element

    let div = document.createElement("div")
    let p = document.createElement("p")
    div.append(p)

    console.log(div.childNodes) // NodeList [ <p> ]

### Appending text

    let div = document.createElement("div")
    div.append("Some text")

    console.log(div.textContent) // "Some text"

### Appending an element and text

    let div = document.createElement("div")
    let p = document.createElement("p")
    div.append("Some text", p)

    console.log(div.childNodes) // NodeList [ #text "Some text", <p> ]

### The append method is unscopable

The `append()` method is not scoped into the `with` statement. See [`Symbol.unscopables`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/unscopables) for more information.

    let div = document.createElement("div")

    with(div) {
      append("foo")
    }
    // ReferenceError: append is not defined

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

- [`Element.prepend()`](prepend)
- [`Node.appendChild()`](../node/appendchild)
- [`ChildNode.after()`](../childnode/after)
- [`Element.insertAdjacentElement()`](insertadjacentelement)
- [`NodeList`](../nodelist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/append" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/append</a>

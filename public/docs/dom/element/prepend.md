# Element.prepend()

The `Element.prepend()` method inserts a set of [`Node`](../node) objects or [`DOMString`](../domstring) objects before the first child of the [`Element`](../element). [`DOMString`](../domstring) objects are inserted as equivalent [`Text`](../text) nodes.

## Syntax

    prepend(...nodesOrDOMStrings);

### Parameters

`nodesOrDOMStrings`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to insert.

### Return value

`undefined`.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Prepending an element

    let div = document.createElement("div");
    let p = document.createElement("p");
    let span = document.createElement("span");
    div.append(p);
    div.prepend(span);

    console.log(div.childNodes); // NodeList [ <span>, <p> ]

### Prepending text

    let div = document.createElement("div");
    div.append("Some text");
    div.prepend("Headline: ");

    console.log(div.textContent); // "Headline: Some text"

### Appending an element and text

    let div = document.createElement("div");
    let p = document.createElement("p");
    div.prepend("Some text", p);

    console.log(div.childNodes); // NodeList [ #text "Some text", <p> ]

### The prepend method is unscopable

The `prepend()` method is not scoped into the `with` statement. See [`Symbol.unscopables`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/unscopables) for more information.

    let div = document.createElement("div");

    with(div) {
      prepend("foo");
    }
    // ReferenceError: prepend is not defined

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

- [`Element.append()`](append)
- [`Node.appendChild()`](../node/appendchild)
- [`Node.insertBefore()`](../node/insertbefore)
- [`ChildNode.before()`](../childnode/before)
- [`Element.insertAdjacentElement()`](insertadjacentelement)
- [`NodeList`](../nodelist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/prepend" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/prepend</a>

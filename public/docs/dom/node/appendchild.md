Node.appendChild()
==================

The `Node.appendChild()` method adds a node to the end of the list of children of a specified parent node. If the given child is a reference to an existing node in the document, `appendChild()` moves it from its current position to the new position (there is no requirement to remove the node from its parent node before appending it to some other node).

This means that a node can't be in two points of the document simultaneously. So if the node already has a parent, the node is first removed, then appended at the new position. The [`Node.cloneNode()`](clonenode) method can be used to make a copy of the node before appending it under the new parent. Note that the copies made with `cloneNode` will not be automatically kept in sync.

If the given child is a [`DocumentFragment`](../documentfragment), the entire contents of the [`DocumentFragment`](../documentfragment) are moved into the child list of the specified parent node.

**Newer API available!**  
The [`Element.append()`](../element/append) method supports multiple arguments and appending strings.

Syntax
------

    element.appendChild(aChild)

### Parameters

`aChild`  
The node to append to the given parent node (commonly an element).

### Return value

The returned value is the appended child (`aChild`), except when `aChild` is a [`DocumentFragment`](../documentfragment), in which case the empty [`DocumentFragment`](../documentfragment) is returned.

Notes
-----

Chaining may not work as expected, due to `appendChild()` returning the child element:

    let aBlock = document.createElement('block').appendChild( document.createElement('b') );

Sets `aBlock` to `<b></b>` only, which is probably not what you want.

Example
-------

    // Create a new paragraph element, and append it to the end of the document body
    let p = document.createElement("p");
    document.body.appendChild(p);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-appendchild">DOM<br />
<span class="small">The definition of 'Node.appendChild()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-3-Core/">Document Object Model (DOM) Level 3 Core Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-184E7107">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.appendChild()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-184E7107">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.appendChild()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-184E7107">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node.appendChild()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`appendChild`

1

12

1

5

7

1.1

1

18

4

10.1

1

1.0

See also
--------

-   [`Node.removeChild()`](removechild)
-   [`Node.replaceChild()`](replacechild)
-   [`Node.insertBefore()`](insertbefore)
-   [`Node.hasChildNodes()`](haschildnodes)
-   [`Element.insertAdjacentElement()`](../element/insertadjacentelement)
-   [`Element.append()`](../element/append)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild</a>

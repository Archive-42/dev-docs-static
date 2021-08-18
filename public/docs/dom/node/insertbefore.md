Node.insertBefore()
===================

The `Node.insertBefore()` method inserts a node before a *reference node* as a child of a specified *parent node*.

If the given node already exists in the document, `insertBefore()` moves it from its current position to the new position. (That is, it will automatically be removed from its existing parent before appending it to the specified new parent.)

This means that a node cannot be in two locations of the document simultaneously.

**Note:** The [`Node.cloneNode()`](clonenode) can be used to make a copy of the node before appending it under the new parent. Note that the copies made with `cloneNode()` will not be automatically kept in sync.

If the given child is a [`DocumentFragment`](../documentfragment), the entire contents of the `DocumentFragment` are moved into the child list of the specified parent node.

Syntax
------

    let insertedNode = parentNode.insertBefore(newNode, referenceNode)

`insertedNode`  
The node being inserted (the same as `newNode`)

`parentNode`  
The parent of the newly inserted node.

`newNode`  
The node to be inserted.

`referenceNode`  
The node before which `newNode` is inserted. If this is `null`, then `newNode` is inserted at the end of `parentNode`'s child nodes.

**Note:** `referenceNode` is **not** an optional parameter. You must explicitly pass a [`Node`](../node) or `null`. Failing to provide it or passing invalid values may [behave](https://code.google.com/p/chromium/issues/detail?id=419780) [differently](https://bugzilla.mozilla.org/show_bug.cgi?id=119489) in different browser versions.

### Return value

Returns the added child (unless `newNode` is a [`DocumentFragment`](../documentfragment), in which case the empty [`DocumentFragment`](../documentfragment) is returned).

Example
-------

### Example 1

    <div id="parentElement">
       <span id="childElement">foo bar</span>
    </div>

    <script>
    // Create the new node to insert
    let newNode = document.createElement("span")

    // Get a reference to the parent node
    let parentDiv = document.getElementById("childElement").parentNode

    // Begin test case [ 1 ] : Existing childElement (all works correctly)
    let sp2 = document.getElementById("childElement")
    parentDiv.insertBefore(newNode, sp2)
    // End test case [ 1 ]

    // Begin test case [ 2 ] : childElement is of Type undefined
    let sp2 = undefined // Non-existent node of id "childElement"
    parentDiv.insertBefore(newNode, sp2) // Implicit dynamic cast to type Node
    // End test case [ 2 ]

    // Begin test case [ 3 ] : childElement is of Type "undefined" ( string )
    let sp2 = "undefined" // Non-existent node of id "childElement"
    parentDiv.insertBefore(newNode, sp2) // Generates "Type Error: Invalid Argument"
    // End test case [ 3 ]
    </script>

### Example 2

    <div id="parentElement">
      <span id="childElement">foo bar</span>
    </div>

    <script>
    // Create a new, plain <span> element
    let sp1 = document.createElement("span")

    // Get the reference element
    let sp2 = document.getElementById("childElement")
    // Get the parent element
    let parentDiv = sp2.parentNode

    // Insert the new element into before sp2
    parentDiv.insertBefore(sp1, sp2)
    </script>

**Note:** There is no `insertAfter()` method. It can be emulated by combining the `insertBefore` method with [`Node.nextSibling`](nextsibling).

In the previous example, `sp1` could be inserted after `sp2` using:

    parentDiv.insertBefore(sp1, sp2.nextSibling)

If `sp2` does not have a next sibling, then it must be the last child — `sp2.nextSibling` returns `null`, and `sp1` is inserted at the end of the child node list (immediately after `sp2`).

### Example 3

Insert an element before the first child element, using the [`firstChild`](firstchild) property.

    // Get the parent element
    let parentElement = document.getElementById('parentElement')
    // Get the parent's first child
    let theFirstChild = parentElement.firstChild

    // Create a new element
    let newElement = document.createElement("div")

    // Insert the new element before the first child
    parentElement.insertBefore(newElement, theFirstChild)

When the element does not have a first child, then `firstChild` is `null`. The element is still appended to the parent, after the last child.

Since the parent element did not have a first child, it did not have a last child, either. Consequently, the newly inserted element is the *only* element.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-insertbefore">DOM<br />
<span class="small">The definition of 'Node.insertBefore' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Fixes errors in the insertion algorithm</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#dom-node-insertbefore">DOM4<br />
<span class="small">The definition of 'Node.insertBefore' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Describes the algorithm in more detail</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-952280727">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.insertBefore' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No notable changes</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-952280727">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.insertBefore' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No notable changes</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#method-insertBefore">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node.insertBefore' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Introduced</td></tr></tbody></table>

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

`insertBefore`

1

12

3

6

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
-   [`Node.appendChild()`](appendchild)
-   [`Node.hasChildNodes()`](haschildnodes)
-   [`Element.insertAdjacentElement()`](../element/insertadjacentelement)
-   [`Element.prepend()`](../element/prepend)
-   [`ChildNode.before()`](../childnode/before)
-   [`ChildNode.after()`](../childnode/after)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore</a>

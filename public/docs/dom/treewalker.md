TreeWalker
==========

The `TreeWalker` object represents the nodes of a document subtree and a position within them.

A `TreeWalker` can be created using the [`Document.createTreeWalker()`](document/createtreewalker) method.

Properties
----------

*This interface doesn't inherit any property.*

 [`TreeWalker.root`](treewalker/root) <span class="badge inline readonly">Read only </span>   
Returns a [`Node`](node) representing the root node as specified when the `TreeWalker` was created.

 [`TreeWalker.whatToShow`](treewalker/whattoshow) <span class="badge inline readonly">Read only </span>   
Returns an `unsigned long` being a bitmask made of constants describing the types of [`Node`](node) that must be presented. Non-matching nodes are skipped, but their children may be included, if relevant. The possible values are:

<table><thead><tr class="header"><th>Constant</th><th>Numerical value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>NodeFilter.SHOW_ALL</code></td><td><code>-1</code> (that is the max value of <code>unsigned long</code>)</td><td>Shows all nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ATTRIBUTE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>2</code></td><td>Shows attribute <a href="attr"><code>Attr</code></a> nodes. This is meaningful only when creating a <a href="treewalker"><code>TreeWalker</code></a> with an <a href="attr"><code>Attr</code></a> node as its root. In this case, it means that the attribute node will appear in the first position of the iteration or traversal. Since attributes are never children of other nodes, they do not appear when traversing over the document tree.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_CDATA_SECTION</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>8</code></td><td>Shows <a href="cdatasection"><code>CDATASection</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_COMMENT</code></td><td><code>128</code></td><td>Shows <a href="comment"><code>Comment</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_DOCUMENT</code></td><td><code>256</code></td><td>Shows <a href="document"><code>Document</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_DOCUMENT_FRAGMENT</code></td><td><code>1024</code></td><td>Shows <a href="documentfragment"><code>DocumentFragment</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_DOCUMENT_TYPE</code></td><td><code>512</code></td><td>Shows <a href="documenttype"><code>DocumentType</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ELEMENT</code></td><td><code>1</code></td><td>Shows <a href="element"><code>Element</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_ENTITY</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>32</code></td><td>Shows <span class="page-not-created"><code>Entity</code></span> nodes. This is meaningful only when creating a <a href="treewalker"><code>TreeWalker</code></a> with an <span class="page-not-created"><code>Entity</code></span> node as its root; in this case, it means that the <span class="page-not-created"><code>Entity</code></span> node will appear in the first position of the traversal. Since entities are not part of the document tree, they do not appear when traversing over the document tree.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ENTITY_REFERENCE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>16</code></td><td>Shows <span class="page-not-created"><code>EntityReference</code></span> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_NOTATION</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>2048</code></td><td>Shows <a href="notation"><code>Notation</code></a> nodes. This is meaningful only when creating a <a href="treewalker"><code>TreeWalker</code></a> with a <a href="notation"><code>Notation</code></a> node as its root; in this case, it means that the <a href="notation"><code>Notation</code></a> node will appear in the first position of the traversal. Since entities are not part of the document tree, they do not appear when traversing over the document tree.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_PROCESSING_INSTRUCTION</code></td><td><code>64</code></td><td>Shows <a href="processinginstruction"><code>ProcessingInstruction</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_TEXT</code></td><td><code>4</code></td><td>Shows <a href="text"><code>Text</code></a> nodes.</td></tr></tbody></table>

 [`TreeWalker.filter`](treewalker/filter) <span class="badge inline readonly">Read only </span>   
Returns a [`NodeFilter`](nodefilter) used to select the relevant nodes.

 [`TreeWalker.expandEntityReferences`](treewalker/expandentityreferences) <span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating, when discarding an <span class="page-not-created">`EntityReference`</span> its whole sub-tree must be discarded at the same time.

[`TreeWalker.currentNode`](treewalker/currentnode)  
Is the [`Node`](node) on which the `TreeWalker` is currently pointing at.

Methods
-------

*This interface doesn't inherit any method.*

**Note**: in the context of a `TreeWalker`, a node is *visible* if it exists in the logical view determined by the `whatToShow` and `filter` parameter arguments. (Whether or not the node is visible on the screen is irrelevant.)

[`TreeWalker.parentNode()`](treewalker/parentnode)  
Moves the current [`Node`](node) to the first *visible* ancestor node in the document order, and returns the found node. It also moves the current node to this one. If no such node exists, or if it is before that the *root node* defined at the object construction, returns `null` and the current node is not changed.

[`TreeWalker.firstChild()`](treewalker/firstchild)  
Moves the current [`Node`](node) to the first *visible* child of the current node, and returns the found child. It also moves the current node to this child. If no such child exists, returns `null` and the current node is not changed.

[`TreeWalker.lastChild()`](treewalker/lastchild)  
Moves the current [`Node`](node) to the last *visible* child of the current node, and returns the found child. It also moves the current node to this child. If no such child exists, `null` is returned and the current node is not changed.

[`TreeWalker.previousSibling()`](treewalker/previoussibling)  
Moves the current [`Node`](node) to its previous sibling, if any, and returns the found sibling. If there is no such node, return `null` and the current node is not changed.

[`TreeWalker.nextSibling()`](treewalker/nextsibling)  
Moves the current [`Node`](node) to its next sibling, if any, and returns the found sibling. If there is no such node, `null` is returned and the current node is not changed.

[`TreeWalker.previousNode()`](treewalker/previousnode)  
Moves the current [`Node`](node) to the previous *visible* node in the document order, and returns the found node. It also moves the current node to this one. If no such node exists, or if it is before that the *root node* defined at the object construction, returns `null` and the current node is not changed.

[`TreeWalker.nextNode()`](treewalker/nextnode)  
Moves the current [`Node`](node) to the next *visible* node in the document order, and returns the found node. It also moves the current node to this one. If no such node exists, returns `null` and the current node is not changed.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-treewalker">DOM<br />
<span class="small">The definition of 'TreeWalker' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Removed the <code>expandEntityReferences</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-TreeWalker">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'TreeWalker' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TreeWalker`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`currentNode`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`expandEntityReferences`

1-41

12-79

4-21

9

9-28

3-10.1

3-41

18-41

4-21

10.1-28

3-10.3

1.0-4.0

`filter`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`firstChild`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`lastChild`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`nextNode`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`nextSibling`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`parentNode`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`previousNode`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`previousSibling`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`root`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

`whatToShow`

1

12

4

9

9

3

3

18

4

10.1

3

1.0

See also
--------

-   The creator method: [`Document.createTreeWalker()`](document/createtreewalker).
-   Related interfaces: [`NodeFilter`](nodefilter), [`NodeIterator`](nodeiterator).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker</a>

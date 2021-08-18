# NodeIterator

The `NodeIterator` interface represents an iterator over the members of a list of the nodes in a subtree of the DOM. The nodes will be returned in document order.

## Syntax

A `NodeIterator` can be created using the [`Document.createNodeIterator()`](document/createnodeiterator) method, as follows:

    const nodeIterator = document.createNodeIterator(root, whatToShow, filter);

## Properties

_This interface doesn't inherit any property._

[`NodeIterator.root`](nodeiterator/root) <span class="badge inline readonly">Read only </span>  
Returns a [`Node`](node) representing the root node as specified when the `NodeIterator` was created.

[`NodeIterator.whatToShow`](nodeiterator/whattoshow) <span class="badge inline readonly">Read only </span>  
Returns an `unsigned long` being a bitmask made of constants describing the types of [`Node`](node) that must to be presented. Non-matching nodes are skipped, but their children may be included, if relevant.

The possible values are:

<table><thead><tr class="header"><th>Constant</th><th>Numerical value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>NodeFilter.SHOW_ALL</code></td><td><code>-1</code> (that is the max value of <code>unsigned long</code>)</td><td>Shows all nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ATTRIBUTE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>2</code></td><td>Shows attribute <a href="attr"><code>Attr</code></a> nodes. This is meaningful only when creating a <a href="nodeiterator"><code>NodeIterator</code></a> with an <a href="attr"><code>Attr</code></a> node as its root; in this case, it means that the attribute node will appear in the first position of the iteration or traversal. Since attributes are never children of other nodes, they do not appear when traversing over the document tree.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_CDATA_SECTION</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>8</code></td><td>Shows <a href="cdatasection"><code>CDATASection</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_COMMENT</code></td><td><code>128</code></td><td>Shows <a href="comment"><code>Comment</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_DOCUMENT</code></td><td><code>256</code></td><td>Shows <a href="document"><code>Document</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_DOCUMENT_FRAGMENT</code></td><td><code>1024</code></td><td>Shows <a href="documentfragment"><code>DocumentFragment</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_DOCUMENT_TYPE</code></td><td><code>512</code></td><td>Shows <a href="documenttype"><code>DocumentType</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ELEMENT</code></td><td><code>1</code></td><td>Shows <a href="element"><code>Element</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_ENTITY</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>32</code></td><td>Shows <span class="page-not-created"><code>Entity</code></span> nodes. This is meaningful only when creating a <a href="nodeiterator"><code>NodeIterator</code></a> with an <span class="page-not-created"><code>Entity</code></span> node as its root; in this case, it means that the <span class="page-not-created"><code>Entity</code></span> node will appear in the first position of the traversal. Since entities are not part of the document tree, they do not appear when traversing over the document tree.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ENTITY_REFERENCE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>16</code></td><td>Shows <span class="page-not-created"><code>EntityReference</code></span> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_NOTATION</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>2048</code></td><td>Shows <a href="notation"><code>Notation</code></a> nodes. This is meaningful only when creating a <a href="nodeiterator"><code>NodeIterator</code></a> with a <a href="notation"><code>Notation</code></a> node as its root; in this case, it means that the <a href="notation"><code>Notation</code></a> node will appear in the first position of the traversal. Since entities are not part of the document tree, they do not appear when traversing over the document tree.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_PROCESSING_INSTRUCTION</code></td><td><code>64</code></td><td>Shows <a href="processinginstruction"><code>ProcessingInstruction</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_TEXT</code></td><td><code>4</code></td><td>Shows <a href="text"><code>Text</code></a> nodes.</td></tr></tbody></table>

[`NodeIterator.filter`](nodeiterator/filter) <span class="badge inline readonly">Read only </span>  
Returns a [`NodeFilter`](nodefilter) used to select the relevant nodes.

[`NodeIterator.expandEntityReferences`](nodeiterator/expandentityreferences) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if, when discarding an <span class="page-not-created">`EntityReference`</span> its whole sub-tree must be discarded at the same time.

[`NodeIterator.referenceNode`](nodeiterator/referencenode) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns the [`Node`](node) to which the iterator is anchored.

[`NodeIterator.pointerBeforeReferenceNode`](nodeiterator/pointerbeforereferencenode) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag that indicates whether the [`NodeIterator`](nodeiterator) is anchored before, the flag being `true`, or after, the flag being `false`, the anchor node.

## Methods

_This interface doesn't inherit any method._

[`NodeIterator.detach()`](nodeiterator/detach) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This operation is a no-op. It doesn't do anything. Previously it was telling the engine that the `NodeIterator` was no more used, but this is now useless.

[`NodeIterator.previousNode()`](nodeiterator/previousnode)  
Returns the previous [`Node`](node) in the document, or `null` if there are none.

[`NodeIterator.nextNode()`](nodeiterator/nextnode)  
Returns the next [`Node`](node) in the document, or `null` if there are none.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#nodeiterator">DOM<br />
<span class="small">The definition of 'NodeIterator' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the <code>referenceNode</code> and <code>pointerBeforeReferenceNode</code> properties.<br />
Removed the <code>expandEntityReferences</code> property.<br />
The method <code>detach()</code> has been changed to be a no-op.<br />
The methods <code>previousNode()</code> and <code>nextNode()</code> don't raise an exception any more.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Iterator-overview">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'NodeIterator' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`NodeIterator`

1

12

3.5

9

9

3

1

18

4

10.1

3

1.0

`detach`

1

12

3.5-22

9

9

3

1

18

4-22

10.1

3

1.0

`expandEntityReferences`

1-41

12-79

3.5-21

9

9-28

3-10.1

1-41

18-41

4-21

10.1-28

3-10.3

1.0-4.0

`filter`

1

12

3.5

9

9

3

1

18

4

10.1

3

1.0

`nextNode`

1

12

3.5

9

9

3

1

18

4

10.1

3

1.0

`pointerBeforeReferenceNode`

1

17

3.5

No

Yes

3

1

18

4

Yes

3

1.0

`previousNode`

1

12

3.5

9

9

3

1

18

4

10.1

3

1.0

`referenceNode`

1

17

3.5

No

Yes

3

1

18

4

Yes

3

1.0

`root`

1

12

3.5

9

9

3

1

18

4

10.1

3

1.0

`whatToShow`

1

12

3.5

9

9

3

1

18

4

10.1

3

1.0

## See also

- The creator method: [`Document.createNodeIterator()`](document/createnodeiterator).
- Related interfaces:
  - [`NodeFilter`](nodefilter)
  - [`TreeWalker`](treewalker)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator</a>

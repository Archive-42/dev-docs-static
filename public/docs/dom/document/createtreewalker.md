# Document.createTreeWalker()

The `Document.createTreeWalker()` creator method returns a newly created [`TreeWalker`](../treewalker) object.

## Syntax

    document.createTreeWalker(root[, whatToShow[, filter[, entityReferenceExpansion]]]);

### Parameters

`root `  
A root [`Node`](../node) of this [`TreeWalker`](../treewalker) traversal. Typically this will be an element owned by the document.

`whatToShow` <span class="badge inline optional">Optional</span>  
A `unsigned long` representing a bitmask created by combining the constant properties of `NodeFilter`. It is a convenient way of filtering for certain types of node. It defaults to `0xFFFFFFFF` representing the `SHOW_ALL` constant.

<table><thead><tr class="header"><th>Constant</th><th>Numerical value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>NodeFilter.SHOW_ALL</code></td><td><code>-1</code> (that is the max value of <code>unsigned long</code>)</td><td>Shows all nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ATTRIBUTE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>2</code></td><td>Shows attribute <a href="../attr"><code>Attr</code></a> nodes. This is meaningful only when creating a <a href="../treewalker"><code>TreeWalker</code></a> with an <a href="../attr"><code>Attr</code></a> node as its root; in this case, it means that the attribute node will appear in the first position of the iteration or traversal. Since attributes are never children of other nodes, they do not appear when traversing over the document tree.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_CDATA_SECTION</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>8</code></td><td>Shows <a href="../cdatasection"><code>CDATASection</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_COMMENT</code></td><td><code>128</code></td><td>Shows <a href="../comment"><code>Comment</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_DOCUMENT</code></td><td><code>256</code></td><td>Shows <a href="../document"><code>Document</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_DOCUMENT_FRAGMENT</code></td><td><code>1024</code></td><td>Shows <a href="../documentfragment"><code>DocumentFragment</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_DOCUMENT_TYPE</code></td><td><code>512</code></td><td>Shows <a href="../documenttype"><code>DocumentType</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ELEMENT</code></td><td><code>1</code></td><td>Shows <a href="../element"><code>Element</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_ENTITY</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>32</code></td><td>Shows <span class="page-not-created"><code>Entity</code></span> nodes. This is meaningful only when creating a <a href="../treewalker"><code>TreeWalker</code></a> with an <span class="page-not-created"><code>Entity</code></span> node as its root; in this case, it means that the <span class="page-not-created"><code>Entity</code></span> node will appear in the first position of the traversal. Since entities are not part of the document tree, they do not appear when traversing over the document tree.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ENTITY_REFERENCE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>16</code></td><td>Shows <span class="page-not-created"><code>EntityReference</code></span> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_NOTATION</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>2048</code></td><td>Shows <a href="../notation"><code>Notation</code></a> nodes. This is meaningful only when creating a <a href="../treewalker"><code>TreeWalker</code></a> with a <a href="../notation"><code>Notation</code></a> node as its root; in this case, it means that the <a href="../notation"><code>Notation</code></a> node will appear in the first position of the traversal. Since entities are not part of the document tree, they do not appear when traversing over the document tree.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_PROCESSING_INSTRUCTION</code></td><td><code>64</code></td><td>Shows <a href="../processinginstruction"><code>ProcessingInstruction</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_TEXT</code></td><td><code>4</code></td><td>Shows <a href="../text"><code>Text</code></a> nodes.</td></tr></tbody></table>

`filter` <span class="badge inline optional">Optional</span>  
A [`NodeFilter`](../nodefilter), that is an object with a method `acceptNode`, which is called by the [`TreeWalker`](../treewalker) to determine whether or not to accept a node that has passed the `whatToShow` check.

`entityReferenceExpansion` <span class="badge inline optional">Optional</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if when discarding an <span class="page-not-created">`EntityReference`</span> its whole sub-tree must be discarded at the same time.

### Return value

A new [`TreeWalker`](../treewalker) object.

## Example

The following example goes through all nodes in the body, reduces the set of nodes to elements, passes through as acceptable each node (it could reduce the set in the `acceptNode()` method instead), and then makes use of tree walker iterator that is created to advance through the nodes (now all elements) and push them into an array.

    var treeWalker = document.createTreeWalker(
      document.body,
      NodeFilter.SHOW_ELEMENT,
      { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
      false
    );

    var nodeList = [];
    var currentNode = treeWalker.currentNode;

    while(currentNode) {
      nodeList.push(currentNode);
      currentNode = treeWalker.nextNode();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createtreewalker">DOM<br />
<span class="small">The definition of 'Document.createTreeWalker' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Removed the <code>expandEntityReferences</code> parameter. Made the <code>whatToShow</code> and <code>filter</code> parameters optionals.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#NodeIteratorFactory-createTreeWalker">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Document.createTreeWalker' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`createTreeWalker`

1

12

1

9

9

3

1

18

4

10.1

3

1.0

`expandEntityReferences`

No

12-79

2-12

9

9-15

3-10.1

No

No

4-14

Yes-14

3-10.3

No

`whatToShow_filter_optional`

4

≤79

12

No

Yes

3

≤37

Yes

14

Yes

3

Yes

## See also

- The interface of the object it creates: [`TreeWalker`](../treewalker).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createTreeWalker" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createTreeWalker</a>

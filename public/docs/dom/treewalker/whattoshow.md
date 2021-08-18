TreeWalker.whatToShow
=====================

The `TreeWalker.whatToShow` read-only property returns an `unsigned long` being a bitmask made of constants describing the types of [`Node`](../node) that must to be presented. Non-matching nodes are skipped, but their children may be included, if relevant. The possible values are:

<table><thead><tr class="header"><th>Constant</th><th>Numerical value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>NodeFilter.SHOW_ALL</code></td><td><code>-1</code> (that is the max value of <code>unsigned long</code>)</td><td>Shows all nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ATTRIBUTE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>2</code></td><td>Shows attribute <a href="../attr"><code>Attr</code></a> nodes. This is meaningful only when creating a <a href="../treewalker"><code>TreeWalker</code></a> with an <a href="../attr"><code>Attr</code></a> node as its root; in this case, it means that the attribute node will appear in the first position of the iteration or traversal. Since attributes are never children of other nodes, they do not appear when traversing over the document tree.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_CDATA_SECTION</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>8</code></td><td>Shows <a href="../cdatasection"><code>CDATASection</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_COMMENT</code></td><td><code>128</code></td><td>Shows <a href="../comment"><code>Comment</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_DOCUMENT</code></td><td><code>256</code></td><td>Shows <a href="../document"><code>Document</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_DOCUMENT_FRAGMENT</code></td><td><code>1024</code></td><td>Shows <a href="../documentfragment"><code>DocumentFragment</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_DOCUMENT_TYPE</code></td><td><code>512</code></td><td>Shows <a href="../documenttype"><code>DocumentType</code></a> nodes.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ELEMENT</code></td><td><code>1</code></td><td>Shows <a href="../element"><code>Element</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_ENTITY</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>32</code></td><td>Shows <span class="page-not-created"><code>Entity</code></span> nodes. This is meaningful only when creating a <a href="../treewalker"><code>TreeWalker</code></a> with an <span class="page-not-created"><code>Entity</code></span> node as its root; in this case, it means that the <span class="page-not-created"><code>Entity</code></span> node will appear in the first position of the traversal. Since entities are not part of the document tree, they do not appear when traversing over the document tree.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_ENTITY_REFERENCE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>16</code></td><td>Shows <span class="page-not-created"><code>EntityReference</code></span> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_NOTATION</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>2048</code></td><td>Shows <a href="../notation"><code>Notation</code></a> nodes. This is meaningful only when creating a <a href="../treewalker"><code>TreeWalker</code></a> with a <a href="../notation"><code>Notation</code></a> node as its root; in this case, it means that the <a href="../notation"><code>Notation</code></a> node will appear in the first position of the traversal. Since entities are not part of the document tree, they do not appear when traversing over the document tree.</td></tr><tr class="even"><td><code>NodeFilter.SHOW_PROCESSING_INSTRUCTION</code></td><td><code>64</code></td><td>Shows <a href="../processinginstruction"><code>ProcessingInstruction</code></a> nodes.</td></tr><tr class="odd"><td><code>NodeFilter.SHOW_TEXT</code></td><td><code>4</code></td><td>Shows <a href="../text"><code>Text</code></a> nodes.</td></tr></tbody></table>

Syntax
------

    nodeTypes = treeWalker.whatToShow;

Example
-------

    var treeWalker = document.createTreeWalker(
        document.body,
        NodeFilter.SHOW_ELEMENT + NodeFilter.SHOW_COMMENT + NodeFilter.SHOW_TEXT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    if( (treeWalker.whatToShow == NodeFilter.SHOW_ALL) ||
        (treeWalker.whatToShow % (NodeFilter.SHOW_COMMENT*2)) >= NodeFilter.SHOW_COMMENT) {
        // treeWalker will show comments
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-treewalker-whattoshow">DOM<br />
<span class="small">The definition of 'TreeWalker.whatToShow' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/">Document Object Model (DOM) Level 2 Traversal and Range Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/traversal.html#Traversal-TreeWalker-whatToShow">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'TreeWalker.whatToShow' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

-   The [`TreeWalker`](../treewalker) interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/whatToShow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TreeWalker/whatToShow</a>

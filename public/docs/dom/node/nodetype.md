Node.nodeType
=============

The read-only `Node.nodeType` property is an integer that identifies what the node is. It distinguishes different kind of nodes from each other, such as [`elements`](../element), [`text`](../text) and [`comments`](../comment).

Syntax
------

    var type = node.nodeType;

Returns an integer which specifies the type of the node. Possible values are listed in [Node type constants](#node_type_constants).

Constants
---------

### Node type constants

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>Node.ELEMENT_NODE</code></td><td><code>1</code></td><td>An <a href="../element"><code>Element</code></a> node like <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p"><code>&lt;p&gt;</code></a> or <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div"><code>&lt;div&gt;</code></a>.</td></tr><tr class="even"><td><code>Node.ATTRIBUTE_NODE</code></td><td><code>2</code></td><td>An <a href="../attr"><code>Attribute</code></a> of an <a href="../element"><code>Element</code></a>.</td></tr><tr class="odd"><td><code>Node.TEXT_NODE</code></td><td><code>3</code></td><td>The actual <a href="../text"><code>Text</code></a> inside an <a href="../element"><code>Element</code></a> or <a href="../attr"><code>Attr</code></a>.</td></tr><tr class="even"><td><code>Node.CDATA_SECTION_NODE</code></td><td><code>4</code></td><td>A <a href="../cdatasection"><code>CDATASection</code></a>, such as <code>&lt;!CDATA[[ … ]]&gt;</code>.</td></tr><tr class="odd"><td><code>Node.PROCESSING_INSTRUCTION_NODE</code></td><td><code>7</code></td><td>A <a href="../processinginstruction"><code>ProcessingInstruction</code></a> of an XML document, such as <code>&lt;?xml-stylesheet … ?&gt;</code>.</td></tr><tr class="even"><td><code>Node.COMMENT_NODE</code></td><td><code>8</code></td><td>A <a href="../comment"><code>Comment</code></a> node, such as <code>&lt;!-- … --&gt;</code>.</td></tr><tr class="odd"><td><code>Node.DOCUMENT_NODE</code></td><td><code>9</code></td><td>A <a href="../document"><code>Document</code></a> node.</td></tr><tr class="even"><td><code>Node.DOCUMENT_TYPE_NODE</code></td><td><code>10</code></td><td>A <a href="../documenttype"><code>DocumentType</code></a> node, such as <code>&lt;!DOCTYPE html&gt;</code>.</td></tr><tr class="odd"><td><code>Node.DOCUMENT_FRAGMENT_NODE</code></td><td><code>11</code></td><td>A <a href="../documentfragment"><code>DocumentFragment</code></a> node.</td></tr></tbody></table>

### Deprecated node type constants <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

The following constants have been deprecated and should not be used anymore.

<table><tbody><tr class="odd"><td>Constant</td><td>Value</td><td>Description</td></tr><tr class="even"><td><code>Node.ENTITY_REFERENCE_NODE</code></td><td>5</td><td>An XML Entity Reference node, such as <code>&amp;foo;</code>. Removed in <a href="https://www.w3.org/TR/dom/">DOM4</a>.</td></tr><tr class="odd"><td><code>Node.ENTITY_NODE</code></td><td>6</td><td>An XML <code>&lt;!ENTITY …&gt;</code> node. Removed in <a href="https://www.w3.org/TR/dom/">DOM4</a>.</td></tr><tr class="even"><td><code>Node.NOTATION_NODE</code></td><td>12</td><td>An XML <code>&lt;!NOTATION …&gt;</code> node. Removed in <a href="https://www.w3.org/TR/dom/">DOM4</a>.</td></tr></tbody></table>

Examples
--------

### Different types of nodes

    document.nodeType === Node.DOCUMENT_NODE; // true
    document.doctype.nodeType === Node.DOCUMENT_TYPE_NODE; // true

    document.createDocumentFragment().nodeType === Node.DOCUMENT_FRAGMENT_NODE; // true

    var p = document.createElement("p");
    p.textContent = "Once upon a time…";

    p.nodeType === Node.ELEMENT_NODE; // true
    p.firstChild.nodeType === Node.TEXT_NODE; // true

### Comments

This example checks if the first node inside the document element is a comment, and displays a message if not.

    var node = document.documentElement.firstChild;
    if (node.nodeType !== Node.COMMENT_NODE) {
      console.warn("You should comment your code!");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-nodetype">DOM<br />
<span class="small">The definition of 'Node.nodeType' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Deprecated <code>ATTRIBUTE_NODE</code>, <code>ENTITY_REFERENCE_NODE</code> and <code>NOTATION_NODE</code> types.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-1950641247">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.nodeType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No changes.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-111237558">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.nodeType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-111237558">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node.nodeType' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`nodeType`

1

12

1

6

7

1.1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeType</a>

Node.nodeValue
==============

The `nodeValue` property of the [`Node`](../node) interface returns or sets the value of the current node.

Syntax
------

    str = node.nodeValue;
    node.nodeValue = str;

### Value

`str` is a string containing the value of the current node, if any. For the document itself, `nodeValue` returns `null`. For text, comment, and CDATA nodes, `nodeValue` returns the content of the node. For attribute nodes, the value of the attribute is returned.

The following table shows the return values for different elements:

<table><thead><tr class="header"><th>Node</th><th>Value of nodeValue</th></tr></thead><tbody><tr class="odd"><td><a href="../cdatasection"><code>CDATASection</code></a></td><td>Content of the CDATA section</td></tr><tr class="even"><td><a href="../comment"><code>Comment</code></a></td><td>Content of the comment</td></tr><tr class="odd"><td><a href="../document"><code>Document</code></a></td><td><code>null</code></td></tr><tr class="even"><td><a href="../documentfragment"><code>DocumentFragment</code></a></td><td><code>null</code></td></tr><tr class="odd"><td><a href="../documenttype"><code>DocumentType</code></a></td><td><code>null</code></td></tr><tr class="even"><td><a href="../element"><code>Element</code></a></td><td><code>null</code></td></tr><tr class="odd"><td><a href="../namednodemap"><code>NamedNodeMap</code></a></td><td><code>null</code></td></tr><tr class="even"><td><span class="page-not-created"><code>EntityReference</code></span></td><td><code>null</code></td></tr><tr class="odd"><td><a href="../notation"><code>Notation</code></a></td><td><code>null</code></td></tr><tr class="even"><td><a href="../processinginstruction"><code>ProcessingInstruction</code></a></td><td>Entire content excluding the target</td></tr><tr class="odd"><td><a href="../text"><code>Text</code></a></td><td>Content of the text node</td></tr></tbody></table>

When `nodeValue` is defined to be `null`, setting it has no effect.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-nodevalue">DOM<br />
<span class="small">The definition of 'Node: nodeValue' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`nodeValue`

1

12

1

6

≤12.1

7

1

18

4

≤12.1

7

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeValue</a>

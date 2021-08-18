Node.nodeName
=============

The `nodeName` read-only property returns the name of the current [`Node`](../node) as a string.

Syntax
------

    var str = node.nodeName;

### Value

A [`DOMString`](../domstring). Values for the different types of nodes are:

<table><thead><tr class="header"><th>Interface</th><th>nodeName value</th></tr></thead><tbody><tr class="odd"><td><a href="../attr"><code>Attr</code></a></td><td>The value of <span class="page-not-created"><code>Attr.name</code></span></td></tr><tr class="even"><td><a href="../cdatasection"><code>CDATASection</code></a></td><td><code>"#cdata-section"</code></td></tr><tr class="odd"><td><a href="../comment"><code>Comment</code></a></td><td><code>"#comment"</code></td></tr><tr class="even"><td><a href="../document"><code>Document</code></a></td><td><code>"#document"</code></td></tr><tr class="odd"><td><a href="../documentfragment"><code>DocumentFragment</code></a></td><td><code>"#document-fragment"</code></td></tr><tr class="even"><td><a href="../documenttype"><code>DocumentType</code></a></td><td>The value of <span class="page-not-created"><code>DocumentType.name</code></span></td></tr><tr class="odd"><td><a href="../element"><code>Element</code></a></td><td>The value of <a href="../element/tagname"><code>Element.tagName</code></a></td></tr><tr class="even"><td><span class="page-not-created"><code>Entity</code></span></td><td>The entity name</td></tr><tr class="odd"><td><span class="page-not-created"><code>EntityReference</code></span></td><td>The name of entity reference</td></tr><tr class="even"><td><a href="../notation"><code>Notation</code></a></td><td>The notation name</td></tr><tr class="odd"><td><a href="../processinginstruction"><code>ProcessingInstruction</code></a></td><td>The value of <span class="page-not-created"><code>ProcessingInstruction.target</code></span></td></tr><tr class="even"><td><a href="../text"><code>Text</code></a></td><td><code>"#text"</code></td></tr></tbody></table>

Example
-------

Given the following markup:

    <div id="d1">hello world</div>
    <input type="text" id="t">

and the following script:

    var div1 = document.getElementById("d1");
    var text_field = document.getElementById("t");

    text_field.value = div1.nodeName;

In XHTML (or any other XML format), `text_field`'s value would read `"div"`. However, in HTML, `text_field`'s value would read `"DIV"`, because `nodeName` and `tagName` return in upper case on HTML elements in DOMs flagged as HTML documents. Read more [details on nodeName case sensitivity in different browsers](http://ejohn.org/blog/nodename-case-sensitivity/).

Note that the [`Element.tagName`](../element/tagname) property could have been used instead, since `nodeName` has the same value as `tagName` for an element. Bear in mind, however, that `nodeName` will return `"#text"` for text nodes while `tagName` will return `undefined`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-nodename">DOM<br />
<span class="small">The definition of 'nodeName' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`nodeName`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeName</a>

Element.getAttributeNodeNS()
============================

Returns the `Attr` node for the attribute with the given namespace and name.

Syntax
------

    attributeNode = element.getAttributeNodeNS(namespace, nodeName)

-   `attributeNode` is the node for specified attribute.
-   `namespace` is a string specifying the namespace of the attribute.
-   `nodeName` is a string specifying the name of the attribute.

<span class="comment">== Example == TBD The example needs to be fixed pre&gt; // html: &lt;div id="top" /&gt; t = document.getElementById("top"); specialNode = t.getAttributeNodeNS( "[http://www.mozilla.org/ns/specialspace](https://www.mozilla.org/ns/specialspace)", "id"); // iNode.value = "full-top" &lt;/pre</span>

Notes
-----

`getAttributeNodeNS` is more specific than [getAttributeNode](getattributenode) in that it allows you to specify attributes that are part of a particular namespace. The corresponding setter method is [setAttributeNodeNS](setattributenodens).

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-getattributenodens">DOM<br />
<span class="small">The definition of 'getAttributeNodeNS()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getAttributeNodeNS`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNodeNS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttributeNodeNS</a>

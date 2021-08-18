Element.removeAttributeNode()
=============================

The `removeAttributeNode()` method of the [`Element`](../element) object removes the specified attribute from the current element.

Syntax
------

    removedAttr = element.removeAttributeNode(attributeNode)

-   attributeNode is the `Attr` node that needs to be removed.
-   removedAttr is the removed `Attr` node.

Example
-------

    // Given: <div id="top" align="center" />
    var d = document.getElementById("top");
    var d_align = d.getAttributeNode("align");
    d.removeAttributeNode(d_align);
    // align is now removed: <div id="top" />

Notes
-----

If the removed attribute has a default value, it is immediately replaced. The replacing attribute has the same namespace URI and local name, as well as the original prefix, when applicable.

There is no `removeAttributeNodeNS` method; the `removeAttributeNode` method can remove both namespaced attributes and non-namespaced attributes.

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-removeattributenode">DOM<br />
<span class="small">The definition of 'Element: removeAttributeNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`removeAttributeNode`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/removeAttributeNode</a>

Element.setAttributeNS()
========================

`setAttributeNS` adds a new attribute or changes the value of an attribute with the given namespace and name.

Syntax
------

    element.setAttributeNS(namespace, name, value)

-   `namespace` is a string specifying the namespace of the attribute.
-   `name` is a string identifying the attribute by its qualified name; that is, a namespace prefix followed by a colon followed by a local name.
-   `value` is the desired string value of the new attribute.

Example
-------

    let d = document.getElementById('d1');
    d.setAttributeNS('http://www.mozilla.org/ns/specialspace', 'spec:align', 'center');

Notes
-----

DOM methods dealing with element's attributes:

<table><thead><tr class="header"><th>Not namespace-aware, most commonly used methods</th><th>Namespace-aware variants (DOM Level 2)</th><th>DOM Level 1 methods for dealing with <code>Attr</code> nodes directly (seldom used)</th><th>DOM Level 2 namespace-aware methods for dealing with <code>Attr</code> nodes directly (seldom used)</th></tr></thead><tbody><tr class="odd"><td><a href="setattribute"><code>setAttribute</code></a> (DOM 1)</td><td><a href="setattributens"><code>setAttributeNS</code></a></td><td><a href="setattributenode"><code>setAttributeNode</code></a></td><td><a href="setattributenodens"><code>setAttributeNodeNS</code></a></td></tr><tr class="even"><td><a href="getattribute"><code>getAttribute</code></a> (DOM 1)</td><td><a href="getattributens"><code>getAttributeNS</code></a></td><td><a href="getattributenode"><code>getAttributeNode</code></a></td><td><a href="getattributenodens"><code>getAttributeNodeNS</code></a></td></tr><tr class="odd"><td><a href="hasattribute"><code>hasAttribute</code></a> (DOM 2)</td><td><a href="hasattributens"><code>hasAttributeNS</code></a></td><td>-</td><td>-</td></tr><tr class="even"><td><a href="removeattribute"><code>removeAttribute</code></a> (DOM 1)</td><td><a href="removeattributens"><code>removeAttributeNS</code></a></td><td><a href="removeattributenode"><code>removeAttributeNode</code></a></td><td>-</td></tr></tbody></table>

`setAttributeNS` is the only method for namespaced attributes which expects the fully qualified name, i.e. `"namespace:localname"`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-setattributens">DOM<br />
<span class="small">The definition of 'document.setAttributeNS' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`setAttributeNS`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttributeNS</a>

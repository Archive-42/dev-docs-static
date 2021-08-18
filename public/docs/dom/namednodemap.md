NamedNodeMap
============

The `NamedNodeMap` interface represents a collection of [`Attr`](attr) objects. Objects inside a `NamedNodeMap` are not in any particular order, unlike [`NodeList`](nodelist), although they may be accessed by an index as in an array.

A `NamedNodeMap` object is *live* and will thus be auto-updated if changes are made to its contents internally or elsewhere.

Although called `NamedNodeMap`, this interface doesn't deal with [`Node`](node) objects but with [`Attr`](attr) objects, which were originally a specialized class of [`Node`](node), and still are in some implementations.

Properties
----------

*This interface doesn't inherit any property.*

 <span class="page-not-created">`NamedNodeMap.length`</span> <span class="badge inline readonly">Read only </span>   
Returns the amount of objects in the map.

Methods
-------

*This interface doesn't inherit any method.*

[`NamedNodeMap.getNamedItem()`](namednodemap/getnameditem)  
Returns a [`Attr`](attr), corresponding to the given name.

<span class="page-not-created">`NamedNodeMap.setNamedItem()`</span>  
Replaces, or adds, the [`Attr`](attr) identified in the map by the given name.

<span class="page-not-created">`NamedNodeMap.removeNamedItem()`</span>  
Removes the [`Attr`](attr) identified by the given map.

<span class="page-not-created">`NamedNodeMap.item()`</span>  
Returns the [`Attr`](attr) at the given index, or `null` if the index is higher or equal to the number of nodes.

<span class="page-not-created">`NamedNodeMap.getNamedItemNS()`</span>  
Returns a [`Attr`](attr) identified by a namespace and related local name.

<span class="page-not-created">`NamedNodeMap.setNamedItemNS()`</span>  
Replaces, or adds, the [`Attr`](attr) identified in the map by the given namespace and related local name.

<span class="page-not-created">`NamedNodeMap.removeNamedItemNS()`</span>  
Removes the [`Attr`](attr) identified by the given namespace and related local name.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-namednodemap">DOM<br />
<span class="small">The definition of 'NamedNodeMap' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Deals with <a href="attr"><code>Attr</code></a> instead of <a href="node"><code>Node</code></a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-1780488922">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'NamedNodeMap' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-1780488922">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'NamedNodeMap' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added <code>getNamedItemNS()</code>, <code>setNamedItemNS()</code> and <code>removeNamedItemNS()</code></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/core.html#ID-1780488922">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'NamedNodeMap' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`NamedNodeMap`

1

12

34

22-34

Yes-22

5

≤12.1

1

1

18

34

22-34

Yes-22

≤12.1

1

1.0

`getNamedItem`

1

12

34

6

≤12.1

1

1

18

34

≤12.1

1

1.0

`getNamedItemNS`

1

12

34

9

≤12.1

1

1

18

34

≤12.1

1

1.0

`item`

1

12

34

5

≤12.1

1

1

18

34

≤12.1

1

1.0

`length`

1

12

34

5

≤12.1

1

1

18

34

≤12.1

1

1.0

`removeNamedItem`

1

12

34

6

≤12.1

1

1

18

34

≤12.1

1

1.0

`removeNamedItemNS`

1

12

34

9

≤12.1

1

1

18

34

≤12.1

1

1.0

`setNamedItem`

1

12

34

6

≤12.1

1

1

18

34

≤12.1

1

1.0

`setNamedItemNS`

1

12

34

9

≤12.1

1

1

18

34

≤12.1

1

1.0

See also
--------

-   [`Element.attributes`](element/attributes)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NamedNodeMap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NamedNodeMap</a>

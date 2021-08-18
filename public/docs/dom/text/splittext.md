Text.splitText()
================

The `Text.splitText()` method breaks the [`Text`](../text) node into two nodes at the specified offset, keeping both nodes in the tree as siblings.

After the split, the current node contains all the content up to the specified offset point, and a newly created node of the same type contains the remaining text. The newly created node is returned to the caller. If the original node had a parent, the new node is inserted as the next sibling of the original node. If the offset is equal to the length of the original node, the newly created node has no data.

Separated text nodes can be concatenated using the [`Node.normalize()`](../node/normalize) method.

Syntax
------

    newNode = textNode.splitText(offset)

### Parameters

`offset`  
The index immediately before which to break the text node.

### Return value

Returns a newly created [`Text`](../text) node that contains the text after the specified offset point.

### Exceptions thrown

A [`DOMException`](../domexception) with a value of `INDEX_SIZE_ERR` is thrown if the specified offset is negative or is greater than the number of 16-bit units in the node's text; a [`DOMException`](../domexception) with a value of `NO_MODIFICATION_ALLOWED_ERR` is thrown if the node is read-only.

Example
-------

In this example, the text of a [`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) is split into two text nodes, and a [`<u>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/u) is inserted between them.

### HTML

    <p>foobar</p>

### JavaScript

    const p = document.querySelector('p');

    // Get contents of <p> as a text node
    const foobar = p.firstChild;

    // Split 'foobar' into two text nodes, 'foo' and 'bar',
    // and save 'bar' as a const
    const bar = foobar.splitText(3);

    // Create a <u> element containing ' new content '
    const u = document.createElement('u');
    u.appendChild(document.createTextNode(' new content '));

    // Add <u> before 'bar'
    p.insertBefore(u, bar);

    // The result is: <p>foo<u> new content </u>bar</p>

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-text-splittext">DOM<br />
<span class="small">The definition of 'Text.splitText' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-3-Core/">Document Object Model (DOM) Level 3 Core Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-38853C1D">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Text.splitText' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-38853C1D">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Text.splitText' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-38853C1D">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Text.splitText' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`splitText`

1

Before Chrome 30, the `offset` argument was optional.

12

1

5

Yes

Before Opera 17, the `offset` argument was optional.

1

The `offset` argument is optional.

Yes

Before version 4.4, the `offset` argument was optional.

18

Before Chrome 30, the `offset` argument was optional.

4

Yes

Before Opera 17, the `offset` argument was optional.

1

The `offset` argument is optional.

1.0

Before Samsung Internet 2.0, the `offset` argument was optional.

See also
--------

-   The [`Text`](../text) interface it belongs to.
-   The opposite method: [`Node.normalize`](../node/normalize).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Text/splitText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Text/splitText</a>

Node.compareDocumentPosition()
==============================

The `Node.compareDocumentPosition()` method reports the position of the given node relative to another node in any document — not just the given node’s document.

The return value is a [bitmask](https://en.wikipedia.org/wiki/Mask_(computing)) of the following values:

<table><thead><tr class="header"><th>Name</th><th>Value</th></tr></thead><tbody><tr class="odd"><td><code>DOCUMENT_POSITION_DISCONNECTED</code></td><td>1</td></tr><tr class="even"><td><code>DOCUMENT_POSITION_PRECEDING</code></td><td>2</td></tr><tr class="odd"><td><code>DOCUMENT_POSITION_FOLLOWING</code></td><td>4</td></tr><tr class="even"><td><code>DOCUMENT_POSITION_CONTAINS</code></td><td>8</td></tr><tr class="odd"><td><code>DOCUMENT_POSITION_CONTAINED_BY</code></td><td>16</td></tr><tr class="even"><td><code>DOCUMENT_POSITION_IMPLEMENTATION_SPECIFIC</code></td><td>32</td></tr></tbody></table>

Syntax
------

    compareMask = node.compareDocumentPosition(otherNode)

### Parameters

`otherNode`  
The other `Node` with which to compare the first *`node`*’s document position.

### Return value

An integer value whose bits represent the `otherNode`'s relationship to the calling `node`.

More than one bit is set if multiple scenarios apply. For example, if `otherNode` is located earlier in the document ***and*** contains the `node` on which `compareDocumentPosition()` was called, then both the `DOCUMENT_POSITION_CONTAINS` and `DOCUMENT_POSITION_PRECEDING` bits would be set, producing a value of 10 (`0x0A`).

Example
-------

    const head = document.head;
    const body = document.body;

    if (head.compareDocumentPosition(body) & Node.DOCUMENT_POSITION_FOLLOWING) {
      console.log('Well-formed document');
    } else {
      console.error('<head> is not before <body>');
    }

**Note:** Because the result returned by `compareDocumentPosition()` is a bitmask, the [bitwise AND operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators) must be used for meaningful results.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-comparedocumentposition">DOM<br />
<span class="small">The definition of 'Node.compareDocumentPosition()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#Node3-compareDocumentPosition">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.compareDocumentPosition()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`compareDocumentPosition`

1

12

9

9

Only supports `contains` for elements

≤12.1

4

1

18

9

≤12.1

3.2

1.0

See also
--------

-   `Node.contains()`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/compareDocumentPosition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/compareDocumentPosition</a>

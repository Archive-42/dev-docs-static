Node.cloneNode()
================

The `Node.cloneNode()` method returns a duplicate of the node on which this method was called.

Syntax
------

    let newClone = node.cloneNode([deep])

`node`  
The node to be cloned.

`newClone`  
The new node, cloned from `node`.

The `newClone` has no parent and is not part of the document, *until* it is added to another node that is part of the document (using [`Node.appendChild()`](appendchild) or a similar method).

 `deep` <span class="badge inline optional">Optional</span>**<sup>\*</sup>**   
If `true`, then `node` and its whole subtree—including text that may be in child [`Text`](../text) nodes—is also copied.

If `false`, only `node` will be cloned. Any text that `node` contains is not cloned, either (since text is contained by one or more child [`Text`](../text) nodes).

`deep` has no effect on empty elements (such as the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) and [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements).

**<sup>\*</sup>Note:** In the DOM4 specification (since Gecko 13.0 (Firefox 13 / Thunderbird 13 / SeaMonkey 2.10)), the optional `deep` argument defaults to `true`.

**This behavior has been changed in the latest spec!** Although `deep` it still optional, it now defaults to `false`.

**You should *always* provide an explicit value for backward and forward compatibility.**

-   With Gecko 28.0 (Firefox 28 / Thunderbird 28 / SeaMonkey 2.25 / Firefox OS 1.3)), the console warned developers not to omit the argument.
-   Starting with Gecko 29.0 (Firefox 29 / Thunderbird 29 / SeaMonkey 2.26)), a shallow clone is defaulted instead of a deep clone.

Example
-------

    let p = document.getElementById("para1")
    let p_prime = p.cloneNode(true)

Notes
-----

Cloning a node copies all of its attributes and their values, including intrinsic (inline) listeners. It does *not* copy event listeners added using [`addEventListener()`](../eventtarget/addeventlistener) or those assigned to element properties (e.g., `node.onclick = someFunction`). Additionally, for a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element, the painted image is not copied.

**Warning:** `cloneNode()` may lead to duplicate element IDs in a document!

If the original node has an [`id attribute`](../element/id), and the clone will be placed in the same document, then you should modify the clone's ID to be unique.

[`Name`](../index) attributes may need to be modified also, depending on whether duplicate names are expected.

To clone a node to insert into a *different* document, use [`Document.importNode()`](../document/importnode) instead.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-clonenode">DOM<br />
<span class="small">The definition of 'Node.cloneNode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-3A0ED0A4">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.cloneNode()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-3A0ED0A4">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.cloneNode()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`cloneNode`

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

`deep_defaults_to_false`

Yes

12

29

13-29

`deep` defaults to `true`.

No

Before Firefox 13, `deep` was a required parameter.

Yes

Yes

Yes

Yes

Yes

29

14-29

`deep` defaults to `true`.

No

Before Firefox 14, `deep` was a required parameter.

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/cloneNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/cloneNode</a>

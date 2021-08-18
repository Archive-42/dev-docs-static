# Node.previousSibling

The `Node.previousSibling` read-only property returns the node immediately preceding the specified one in its parent's [`childNodes`](childnodes) list, or `null` if the specified node is the first in that list.

## Syntax

    previousNode = node.previousSibling;

## Examples

The following examples demonstrate how `previousSibling` works with and without text nodes mixed in with elements.

### First example

In this example, we have a series of `img` elements directly adjacent to each other, with no whitespace between them.

    <img id="b0"><img id="b1"><img id="b2">

    document.getElementById("b1").previousSibling;    // <img id="b0">
    document.getElementById("b2").previousSibling.id; // "b1"

### Second example

In this example, there are whitespace text nodes (line breaks) between the `img` elements.

    <img id="b0">
    <img id="b1">
    <img id="b2">

    document.getElementById("b1").previousSibling;                 // #text
    document.getElementById("b1").previousSibling.previousSibling; // <img id="b0">
    document.getElementById("b2").previousSibling.previousSibling; // <img id="b1">
    document.getElementById("b2").previousSibling;                 // #text
    document.getElementById("b2").previousSibling.id;              // undefined

## Notes

Gecko-based browsers insert text nodes into a document to represent whitespace in the source markup. Therefore a node obtained, for example, using [`Node.firstChild`](firstchild) or [`Node.previousSibling`](previoussibling) may refer to a whitespace text node rather than the actual element the author intended to get. You can use `previousElementSibling` to get the previous element node (skipping text nodes and any other non-element nodes).

See [Whitespace in the DOM](../document_object_model/whitespace) and [W3C DOM 3 FAQ: Why are some Text nodes empty?](https://www.w3.org/DOM/faq.html#emptytext) for more information.

To navigate the opposite way through the child nodes list use [Node.nextSibling](nextsibling).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-previoussibling">DOM<br />
<span class="small">The definition of 'Node.previousSibling' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-640FB3C8">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.previousSibling' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-640FB3C8">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.previousSibling' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#attribute-previousSibling">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node.previousSibling' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

`previousSibling`

1

12

1

5.5

≤12.1

7

1

18

4

≤12.1

7

1.0

## See also

- [`Node.nextSibling`](nextsibling)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/previousSibling" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/previousSibling</a>

# Node.lastChild

The `Node.lastChild` read-only property returns the last child of the node. If its parent is an element, then the child is generally an element node, a text node, or a comment node. It returns `null` if there are no child elements.

## Syntax

    var childNode = node.lastChild;

## Example

    var tr = document.getElementById("row1");
    var corner_td = tr.lastChild;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-lastchild">DOM<br />
<span class="small">The definition of 'Node.lastChild' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-61AD09FB">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.lastChild' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-61AD09FB">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.lastChild' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-61AD09FB">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node.lastChild' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`lastChild`

1

12

1

6

≤12.1

7

1

18

45

≤12.1

7

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/lastChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/lastChild</a>

# Node.childNodes

The `Node.childNodes` read-only property returns a live [`NodeList`](../nodelist) of child [`nodes`](../node) of the given element where the first child node is assigned index 0. Child nodes include elements, text and comments.

## Syntax

    let nodeList = elementNodeReference.childNodes;

## Examples

### Simple usage

    // parg is an object reference to a <p> element

    // First check that the element has child nodes
    if (parg.hasChildNodes()) {
      let children = parg.childNodes;

      for (let i = 0; i < children.length; i++) {
        // do something with each child as children[i]
        // NOTE: List is live! Adding or removing children will change the list's `length`
      }
    }

### Remove all children from a node

    // This is one way to remove all children from a node
    // box is an object reference to an element

    while (box.firstChild) {
        //The list is LIVE so it will re-index each call
        box.removeChild(box.firstChild);
    }

## Notes

The items in the collection of nodes are objects, not strings. To get data from node objects, use their properties. (For example, to get the name of the first childNode: `elementNodeReference.childNodes[0].nodeName`.)

The `document` object itself has 2 children: the Doctype declaration and the root element, typically referred to as `documentElement`. (In (X)HTML documents this is the `HTML` element.)

`childNodes` includes _all_ child nodes—including non-element nodes like text and comment nodes. To get a collection of only elements, use [`Element.children`](../element/children) instead.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-childnodes">DOM<br />
<span class="small">The definition of 'Node.childNodes' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-1451460987">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.childNodes' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-1451460987">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.childNodes' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-1451460987">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node.childNodes' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`childNodes`

1

12

1

5

7

1.2

1

18

4

10.1

1

1.0

## See also

- [`Node.firstChild`](firstchild)
- [`Node.lastChild`](lastchild)
- [`Node.nextSibling`](nextsibling)
- [`Node.previousSibling`](previoussibling)
- [`Element.children`](../element/children)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/childNodes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/childNodes</a>

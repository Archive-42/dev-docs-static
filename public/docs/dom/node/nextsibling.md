Node.nextSibling
================

The `Node.nextSibling` read-only property returns the node immediately following the specified one in their parent's [`childNodes`](childnodes), or returns `null` if the specified node is the last child in the parent element.

Syntax
------

    nextNode = node.nextSibling

Notes
-----

Gecko-based browsers insert text nodes into a document to represent whitespace in the source markup. Therefore a node obtained, for example, using [`Node.firstChild`](firstchild) or [`Node.previousSibling`](previoussibling) may refer to a whitespace text node rather than the actual element the author intended to get.

See [Whitespace in the DOM](../document_object_model/whitespace) and [W3C DOM 3 FAQ: Why are some Text nodes empty?](https://www.w3.org/DOM/faq.html#emptytext) for more information.

[`Element.nextElementSibling`](../element/nextelementsibling) may be used to obtain the next element skipping any whitespace nodes, other between-element text, or comments.

Example
-------

    <div id="div-1">Here is div-1</div>
    <div id="div-2">Here is div-2</div>

    <script>
    var el = document.getElementById('div-1').nextSibling,
        i = 1;

    console.group('Siblings of div-1:');

    while (el) {
      console.log(i, '. ', el.nodeName);
      el = el.nextSibling;
      i++;
    }

    console.groupEnd();
    </script>

    /**************************************************
      The console displays the following:

         Siblings of div-1

          1. #text
          2. DIV
          3. #text
          4. SCRIPT

    **************************************************/

In the above example, `#text` nodes are inserted in the DOM where whitespace occurs between tags (i.e. after the closing tag of an element and before the opening tag of the next).

The possible inclusion of text nodes must be allowed for when traversing the DOM using `nextSibling`. See the resources [in the Notes section](#notes).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-nextsibling">DOM<br />
<span class="small">The definition of 'Node.nextSibling' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-6AC54C2F">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.nextSibling' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#attribute-nextSibling">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node.nextSibling' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`nextSibling`

1

12

1

5.5

7

1.1

1

18

4

10.1

1

1.0

See also
--------

-   [`Element.nextElementSibling`](../element/nextelementsibling)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/nextSibling" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/nextSibling</a>

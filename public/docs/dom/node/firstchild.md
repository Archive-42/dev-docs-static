# Node.firstChild

The `Node.firstChild` read-only property returns the node's first child in the tree, or `null` if the node has no children. If the node is a `Document`, it returns the first node in the list of its direct children.

## Syntax

    var childNode = node.firstChild;

## Example

This example demonstrates the use of `firstChild` and how whitespace nodes might interfere with using this property.

    <p id="para-01">
      <span>First span</span>
    </p>

    <script>
      var p01 = document.getElementById('para-01');
      console.log(p01.firstChild.nodeName);
    </script>

In the above, the [console](../console) will show '\#text' because a text node is inserted to maintain the whitespace between the end of the opening `<p>` and `<span>` tags. **Any** [whitespace](../document_object_model/whitespace) will create a `#text` node, from a single space to multiple spaces, returns, tabs, and so on.

Another `#text` node is inserted between the closing `</span>` and `</p>`tags.

If this whitespace is removed from the source, the \#text nodes are not inserted and the span element becomes the paragraph's first child.

    <p id="para-01"><span>First span</span></p>

    <script>
      var p01 = document.getElementById('para-01');
      console.log(p01.firstChild.nodeName);
    </script>

Now the console will show 'SPAN'.

To avoid the issue with `node.firstChild` returning `#text` or `#comment` nodes, [`Element.firstElementChild`](../element/firstelementchild) can be used to return only the first element node. However, `node.firstElementChild` requires a shim for Internet Explorer 9 and earlier.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-firstchild">DOM<br />
<span class="small">The definition of 'Node.firstChild' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-169727388">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.firstChild' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-169727388">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.firstChild' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-169727388">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node.firstChild' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`firstChild`

1

12

1

6

≤12.1

7

1

18

4

≤12.1

7

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/firstChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/firstChild</a>

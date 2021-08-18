# Node.isSameNode()

The `isSameNode()` method for `Node` objects tests whether two nodes are the same (that is, whether they reference the same object).

## Syntax

    const isSameNode = node.isSameNode(otherNode)

### Parameters

- `otherNode` The [`Node`](../node) to test against.

## Example

In this example, we create three [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) blocks. The first and third have the same contents and attributes, while the second is different. Then we run some JavaScript to compare the nodes using `isSameNode()` and output the results.

### HTML

    <div>This is the first element.</div>
    <div>This is the second element.</div>
    <div>This is the first element.</div>

    <p id="output"></p>

### JavaScript

    let output = document.getElementById("output");
    let divList  = document.getElementsByTagName("div");

    output.innerHTML += "div 0 same as div 0: " + divList[0].isSameNode(divList[0]) + "<br/>";
    output.innerHTML += "div 0 same as div 1: " + divList[0].isSameNode(divList[1]) + "<br/>";
    output.innerHTML += "div 0 same as div 2: " + divList[0].isSameNode(divList[2]) + "<br/>";

### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-issamenode">DOM<br />
<span class="small">The definition of 'Node: isSameNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change (was for a long time removed from it).</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#Node3-isSameNode">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.isSameNode()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`isSameNode`

1

12

48

1-10

9

≤12.1

3

1

18

48

4-10

≤12.1

1

1.0

## See also

- [`Node.isEqualNode()`](isequalnode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/isSameNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/isSameNode</a>

Node.isEqualNode()
==================

The `Node.isEqualNode()` method tests whether two nodes are equal. Two nodes are equal when they have the same type, defining characteristics (for elements, this would be their ID, number of children, and so forth), its attributes match, and so on. The specific set of data points that must match varies depending on the types of the nodes.

Syntax
------

    var isEqualNode = node.isEqualNode(otherNode);

-   `otherNode`: The [`Node`](../node) to compare equality with.

Example
-------

In this example, we create three [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) blocks. The first and third have the same contents and attributes, while the second is different. Then we run some JavaScript to compare the nodes using `isEqualNode()` and output the results.

### HTML

    <div>This is the first element.</div>
    <div>This is the second element.</div>
    <div>This is the first element.</div>

    <p id="output"></p>

### JavaScript

    let output = document.getElementById("output");
    let divList  = document.getElementsByTagName("div");

    output.innerHTML += "div 0 equals div 0: " + divList[0].isEqualNode(divList[0]) + "<br/>";
    output.innerHTML += "div 0 equals div 1: " + divList[0].isEqualNode(divList[1]) + "<br/>";
    output.innerHTML += "div 0 equals div 2: " + divList[0].isEqualNode(divList[2]) + "<br/>";

### Results

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-isequalnode">DOM<br />
<span class="small">The definition of 'Node.isEqualNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`isEqualNode`

1

12

2

9

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   [`Node.isSameNode()`](issamenode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/isEqualNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/isEqualNode</a>

Node.normalize()
================

The `Node.normalize()` method puts the specified node and all of its sub-tree into a "normalized" form. In a normalized sub-tree, no text nodes in the sub-tree are empty and there are no adjacent text nodes.

Syntax
------

    element.normalize();

Example
-------

    let wrapper = document.createElement("div");

    wrapper.appendChild( document.createTextNode("Part 1 ") );
    wrapper.appendChild( document.createTextNode("Part 2 ") );

    // At this point, wrapper.childNodes.length === 2
    // wrapper.childNodes[0].textContent === "Part 1 "
    // wrapper.childNodes[1].textContent === "Part 2 "

    wrapper.normalize();

    // Now, wrapper.childNodes.length === 1
    // wrapper.childNodes[0].textContent === "Part 1 Part 2 "

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-normalize">DOM<br />
<span class="small">The definition of 'Node: normalize' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`normalize`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

See also
--------

-   [`Text.splitText()`](../text/splittext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/normalize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/normalize</a>

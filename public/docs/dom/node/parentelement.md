Node.parentElement
==================

The `Node.parentElement` read-only property returns the DOM node's parent [`Element`](../element), or `null` if the node either has no parent, or its parent isn't a DOM [`Element`](../element).

Syntax
------

    parentElement = node.parentElement

`parentElement` is the parent element of the current node. This is always a DOM [`Element`](../element) object, or `null`.

Example
-------

    if (node.parentElement) {
        node.parentElement.style.color = "red";
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-parentelement">DOM<br />
<span class="small">The definition of '<code>parentElement</code>' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`parentElement`

1

12

9

9

Only supported on `Element`.

7

Before Opera 15, this feature was only supported on `Element`.

1.1

1

18

9

10.1

Before Opera Android 14, this feature was only supported on `Element`.

1

1.0

On some browsers, the `parentElement` property is only defined on nodes that are themselves an [`Element`](../element). In particular, it is not defined on text nodes.

See also
--------

-   [`Node.parentNode`](parentnode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/parentElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/parentElement</a>

NodeIterator.pointerBeforeReferenceNode
=======================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NodeIterator.pointerBeforeReferenceNode` read-only property returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag that indicates whether the [`NodeFilter`](../nodefilter) is anchored before (if this value is `true`) or after (if this value is `false`) the anchor node indicated by the [`NodeIterator.referenceNode`](referencenode) property.

Syntax
------

    flag = nodeIterator.pointerBeforeReferenceNode;

Example
-------

    var nodeIterator = document.createNodeIterator(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { return NodeFilter.FILTER_ACCEPT; } },
        false
    );
    flag = nodeIterator.pointerBeforeReferenceNode;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-nodeiterator-pointerbeforereferencenode">DOM<br />
<span class="small">The definition of 'NodeIterator.pointerBeforeReferenceNode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pointerBeforeReferenceNode`

1

17

3.5

No

Yes

3

1

18

4

Yes

3

1.0

See also
--------

-   The interface it belongs to: [`NodeIterator`](../nodeiterator)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/pointerBeforeReferenceNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NodeIterator/pointerBeforeReferenceNode</a>

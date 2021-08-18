Range.intersectsNode()
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `Range.intersectsNode()` method returns a boolean indicating whether the given [`Node`](../node) intersects the [`Range`](../range).

Syntax
------

    bool = range.intersectsNode( referenceNode )

### Parameters

*referenceNode*  
The [`Node`](../node) to compare with the [`Range`](../range).

Example
-------

    var range = document.createRange();

    range.selectNode(document.getElementsByTagName("div").item(0));
    var bool = range.intersectsNode(document.getElementsByTagName("p").item(0));

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-intersectsnode">DOM<br />
<span class="small">The definition of 'Range.intersectNode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`intersectsNode`

1

17

17

No

≤12.1

3

1

18

19

≤12.1

1

1.0

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/intersectsNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/intersectsNode</a>

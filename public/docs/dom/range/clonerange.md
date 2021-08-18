Range.cloneRange()
==================

The `Range.cloneRange()` method returns a [`Range`](../range) object with boundary points identical to the cloned [`Range`](../range).

The returned clone is copied by value, not reference, so a change in either [`Range`](../range) does not affect the other.

Syntax
------

    clone = range.cloneRange();

Example
-------

    range = document.createRange();
    range.selectNode(document.getElementsByTagName("div").item(0));
    clone = range.cloneRange();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-clonerange">DOM<br />
<span class="small">The definition of 'Range.cloneRange()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-clone">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.cloneRange()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`cloneRange`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/cloneRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/cloneRange</a>

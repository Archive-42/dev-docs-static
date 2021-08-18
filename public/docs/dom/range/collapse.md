Range.collapse()
================

The `Range.collapse()` method collapses the [`Range`](../range) to one of its boundary points.

A collapsed [`Range`](../range) is empty, containing no content, specifying a single-point in a DOM tree. To determine if a [`Range`](../range) is already collapsed, see the [`Range.collapsed`](collapsed) property.

Syntax
------

    range.collapse(toStart);

### Parameters

 `toStart` <span class="badge inline optional">Optional</span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value: `true` collapses the [`Range`](../range) to its start, `false` to its end. If omitted, it defaults to `false` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>.

Example
-------

    var range = document.createRange();

    referenceNode = document.getElementsByTagName("div").item(0);
    range.selectNode(referenceNode);
    range.collapse(true);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-range-collapse">DOM<br />
<span class="small">The definition of 'Range.collapse()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>The parameter is now optional and default to <code>false</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Traversal-Range/ranges.html#Level2-Range-method-collapse">Document Object Model (DOM) Level 2 Traversal and Range Specification<br />
<span class="small">The definition of 'Range.collapse()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial specification.</td></tr></tbody></table>

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

`collapse`

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

`toStart_parameter_optional`

Yes

≤79

25

No

Optional but defaults to `true`.

15

Yes

Yes

Yes

25

14

Yes

Yes

See also
--------

-   [The DOM interfaces index](../document_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/collapse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/collapse</a>

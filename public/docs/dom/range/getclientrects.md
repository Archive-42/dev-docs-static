Range.getClientRects()
======================

The `Range.getClientRects()` method returns a list of [`DOMRect`](../domrect) objects representing the area of the screen occupied by the [range](../range). This is created by aggregating the results of calls to [`Element.getClientRects()`](../element/getclientrects) for all the elements in the range.

Syntax
------

    rectList = range.getClientRects()

Example
-------

    range = document.createRange();
    range.selectNode(document.getElementsByTagName("div").item(0));
    rectList = range.getClientRects();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-range-getclientrects">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Range.getClientRects()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getClientRects`

4

12

4

9

≤12.1

5

≤37

18

4

≤12.1

4

1.0

See also
--------

-   [`Range`](../range)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Range/getClientRects" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Range/getClientRects</a>

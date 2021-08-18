Window.convertPointFromNodeToPage()
===================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Given a [`Point`](../point) specified in a particular DOM [`Node`](../node)'s coordinate system, the [`Window`](../window) method `convertPointFromNodeToPage()` returns a `Point` which specifies the same position in the page's coordinate system. This method is non-standard and *should not be used*.

Please review the [Browser compatibility](#browser_compatibility) section before using this method, as it's not widely supported (nor is the [`Point`](../point) object it uses).

Syntax
------

    Point = Window.convertPointFromNodeToPage(node, nodePoint);

### Parameters

`node`  
The [`Node`](../node) in whose coordinate system the `Point` specified by `nodePoint` is described.

`nodePoint`  
A [`Point`](../point) object describing a point in `node`'s coordinate system; this point will be converted to the page's coordinate system.

### Return value

A [`Point`](../point) object specifying a point in the page's coordinate system.

Specifications
--------------

This method was specified in [the defunct 20 March 2009 Working Draft of CSS 2D Transforms Module Level 3](https://www.w3.org/TR/2009/WD-css3-2d-transforms-20090320/). It is not present in the current CSS Transforms Module Level 1 Working Draft.

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

`convertPointFromNodeToPage`

Yes-39

No

No

No

Yes-26

Yes

Yes-39

Yes-39

No

Yes-26

Yes

Yes-4.0

See also
--------

-   [`Window.convertPointFromPageToNode()`](convertpointfrompagetonode)
-   Mozilla implementation bug: [bug 850806](https://bugzilla.mozilla.org/show_bug.cgi?id=850806)
-   [`webkitConvertPointFromNodeToPage` documentation at IE Dev Center](https://msdn.microsoft.com/en-us/library/ie/dn760734%28v=vs.85%29.aspx)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/convertPointFromNodeToPage" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/convertPointFromNodeToPage</a>

Element.msZoomTo()
==================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msZoomTo` method scrolls and/or zooms an element to its specified coordinate with animation.

Zoomed elements can expose their zoom level through `msContentZoom` (ie. scrollTop/Left). The zoom level can be reset with `msZoomTo`.

This proprietary method is specific to Internet Explorer and Microsoft Edge.

### Syntax

    Element.msZoomTo(arguments);

### Parameters

**args**\[in\]

Type: MSZoomToOptions

*contentX*\[in\]: The x-coordinate of the content that is the target of the scroll/zoom. If no value is specified, defaults to the current centerpoint of visible content, horizontally.

*contentY*\[in\]: The y-coordinate of the content that is the target of the scroll/zoom. If no value is specified, defaults to the current centerpoint of visible content, vertically.

*viewportX*\[in\]: The alignment point of the viewport. The scroll/zoom operation attempts to align this point with the contentX point.

-   center: Default. Aligns the horizontal center of the viewport to the element's contentX value.
-   left: Aligns the left-most point of the viewport to the element's contentX value.
-   right: Aligns the right-most point of the viewport to the element's contentX value.
-   integer: Aligns the specified x-coordinate of the viewport to the element's contentX value.

*viewportY*\[in\]: The alignment point of the viewport. The scroll/zoom operation attempts to align this point with the contentY point.

-   middle: Default. Aligns the vertical center of the viewport to the element's contentY value.
-   top: Aligns the top-most point of the viewport to the element's contentY value.
-   bottom: Aligns the bottom-most point of the viewport to the element's contentY value.
-   integer: Aligns the specified y-coordinate of the viewport to the element's contentY value.

*scaleFactor*\[in\]: Floating-point. The scale factor (msContentZoomFactor) to zoom to. If no value is specified, defaults to the current zoom level (no additional zoom occurs).This argument is ignored if the element is not zoomable.

*animate*\[in\]: The type of animation to use.

-   default: Uses the default animation.
-   none: No animation is used.

This method has no scrolling effect on non-scrollable elements and no zooming effect on non-zoomable elements (e.g., elements with "-ms-content-zooming: none").

This method has no effect if called from a parent document to scroll or zoom content hosted in an iframe.

### Return value

This method does not return a value.

Example
-------

    /* Zooming in on an element while still keeping it centered in the viewport */
    var args = {
        contentX: target.offsetLeft + target.offsetWidth/2;
        contentY: target.offsetTop + target.offsetHeight/2;
        scaleFactor: 2.0;
    }
    zoomer.msZoomTo(args);

See also
--------

-   [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/msZoomTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/msZoomTo</a>

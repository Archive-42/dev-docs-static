HTMLVideoElement.msStereo3DPackingMode
======================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msStereo3DPackingMode` is a read/write property which gets or sets the frame-packing mode for stereo 3-D video content.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

Syntax
------

    HTMLVideoElement.msStereo3DPackingMode(topbottom, sidebyside, none);

Value
-----

The following values return, or set, the stereo 3-D content packing as "topbottom", "sidebyside", or "none" for regular 2-D video.

-   `none (0)`: Specifies regular 2-D video.
-   `topbottom (1)`: Specifies stereo 3-D content packing and that the views are packed side-by-side in a single frame.
-   `sidebyside (2)`: Specifies sidebyside stereo 3-D content packing and that the views are packed top-to-bottom in a single frame.

See also
--------

-   [HTMLVideoElement](../htmlvideoelement)
-   [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msStereo3DPackingMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msStereo3DPackingMode</a>

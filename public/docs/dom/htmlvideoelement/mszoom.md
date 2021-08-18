HTMLVideoElement.msZoom
=======================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msZoom` is a read/write property which gets or sets whether the video frame is trimmed, on the top and bottom or left and right, to fit the video display.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

Syntax
------

    HTMLVideoElement.msZoom;

Value
-----

Boolean value set to *true* trims the video frame to the display space. Set to *false* the video frame uses letter box or pillarbox to display video.

If the native aspect ratio of a video frame, which is defined by the `videoWidth` and `videoHeight` attributes, does not match the aspect ratio of the `Video` tag, which is defined by the width and height attributes, the video is rendered with letterbox or pillarbox format. Letterbox and pillarbox are the black bars on either the left and right of the video or the top and bottom of the video.

When the `msZoom` attribute is set to *true*, the rendered video is trimmed to fit the dimensions of the video object. Either the top and bottom of the video is trimmed or the left and right of the video is trimmed.

For instance, if the layout space for the video tag is a 4:3 aspect ratio, but the stream coming in is in 16:9 aspect ratio, the `msZoom` option can be used to render the 16:9 video in 4:3 aspect ratio. The rendered video will then take up the full space of the video object.

Example
-------

This examples gets a Video object and sets the `msZoom` property to true.

        var myVideo = document.getElementById("videoTag1");
           myVideo.msZoom = true;
           myVideo.play();

See also
--------

-   [HTMLVideoElement](../htmlvideoelement)
-   [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msZoom" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msZoom</a>
HTMLVideoElement.msHorizontalMirror
===================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msHorizontalMirror` is a read/write property which gets or sets whether a [video](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element is flipped horizontally in the display.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

Syntax
------

    HTMLVideoElement.msHorizontalMirror: boolean;

Value
-----

Boolean value set to *true* flips the video playback horizontally.

Video perspective is flipped on a horizontal axis - this may be useful for playback of a webcam video, providing the user with better mirroring of their real behaviors (ie. when user moves left, their representation on-screen would move left as well).

Example
-------

           var myVideo = document.getElementById("videoTag1");
           myVideo.msHorizontalMirror = true;
           myVideo.play();

Example \#2:

        var flip = document.querySelector('#flip');
        flip.addEventListener('click', function() {
          video.msHorizontalMirror = true;
        });

See also
--------

-   [`HTMLVideoElement`](../htmlvideoelement)
-   [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msHorizontalMirror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msHorizontalMirror</a>

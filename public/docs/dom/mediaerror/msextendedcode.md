MediaError.msExtendedCode
=========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

In the event of an error, the media element's error event will be fired. The element's error property will then contain an `msExtendedCode` read-only property with platform-specific error code information.

`msExtendedCode` is a read-only proprietary property specific to Internet Explorer and Microsoft Edge.

Value
-----

Type: **long**; The platform specific error code.

Example
-------

    var video1 = object.getElementById("video1");

    video1.addEventListener('error', function () {
      var error = video1.error.msExtendedCode;
      //...
    }, false);

    video.addEventListener('canplay', function () {
      video1.play();
    }, false);

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaError/msExtendedCode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaError/msExtendedCode</a>

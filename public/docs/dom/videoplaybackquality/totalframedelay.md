VideoPlaybackQuality.totalFrameDelay
====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `VideoPlaybackQuality.totalFrameDelay` read-only property returns a `double` containing the sum of the frame delay since the creation of the associated [`HTMLVideoElement`](../htmlvideoelement). The frame delay is the difference between a frame's theoretical presentation time and its effective display time.

Syntax
------

    value = videoPlaybackQuality.totalFrameDelay;

Example
-------

    var videoElt = document.getElementById('my_vid');
    var quality = videoElt.getVideoPlaybackQuality();

    alert(quality.totalFrameDelay);

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

`totalFrameDelay`

23

12

No

11

Only works on Windows 8+.

15

8

4.4.3

?

No

14

No

?

See also
--------

-   The [`HTMLVideoElement.getVideoPlaybackQuality()`](../htmlvideoelement/getvideoplaybackquality) method for constructing and returning this interface.
-   [`MediaSource`](../mediasource)
-   [`SourceBuffer`](../sourcebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/totalFrameDelay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/totalFrameDelay</a>

VideoPlaybackQuality.creationTime
=================================

The read-only `creationTime` property on the [`VideoPlaybackQuality`](../videoplaybackquality) interface reports the number of milliseconds since the browsing context was created this quality sample was recorded.

Syntax
------

    value = videoPlaybackQuality.creationTime;

### Value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) object which indicates the number of milliseconds that elapased between the time the browsing context was created and the time at which this sample of the video quality was obtained.

For details on how the time is determined, see [`Performance.now()`](../performance/now).

Example
-------

This example calls `getVideoPlaybackQuality()` to obtain a [`VideoPlaybackQuality`](../videoplaybackquality) object, then determines what percentage of frames have been lost by either corruption or being dropped. If that exceeds 10% (0.1), a function called `lostFramesThresholdExceeded()` is called to, perhaps, update a quality indicator to show an increase in frame loss.

    var videoElem = document.getElementById("my_vid");
    var quality = videoElem.getVideoPlaybackQuality();

    if ((quality.corruptedVideoFrames + quality.droppedVideoFrames)/quality.totalVideoFrames > 0.1) {
      lostFramesThresholdExceeded();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-playback-quality/#videoplaybackquality-interface">Media Playback Quality<br />
<span class="small">The definition of 'VideoPlaybackQuality.corruptedVideoFrames' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`creationTime`

23

12

42

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

-   The [`HTMLVideoElement.getVideoPlaybackQuality()`](../htmlvideoelement/getvideoplaybackquality) method, which returns `VideoPlaybackQuality` objects

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/creationTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/creationTime</a>

VideoPlaybackQuality.totalVideoFrames
=====================================

The [`VideoPlaybackQuality`](../videoplaybackquality) interface's `totalVideoFrames` read-only property returns the total number of video frames that have been displayed or dropped since the media was loaded.

Syntax
------

    value = videoPlaybackQuality.totalVideoFrames;

### Value

The total number of frames that the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element has displayed or dropped since the media was loaded into it. Essentially, this is the number of frames the element *would have presented* had no problems occurred.

This value is reset when the media is reloaded or replaced.

Example
-------

This example calls [`getVideoPlaybackQuality()`](../htmlvideoelement/getvideoplaybackquality) to obtain a [`VideoPlaybackQuality`](../videoplaybackquality) object, then determines what percentage of frames have been lost by either corruption or being dropped. If that exceeds 10% (0.1), a function called `lostFramesThresholdExceeded()` is called to, perhaps, update a quality indicator to show an increase in frame loss.

    var videoElem = document.getElementById("my_vid");
    var quality = videoElem.getVideoPlaybackQuality();

    if ((quality.corruptedVideoFrames + quality.droppedVideoFrames)/quality.totalVideoFrames > 0.1) {
      lostFramesThresholdExceeded();
    }

A similar algorithm might be used to attempt to switch to a lower-resolution video that requires less bandwidth, in order to avoid dropping frames.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-playback-quality/#videoplaybackquality-interface">Media Playback Quality<br />
<span class="small">The definition of 'VideoPlaybackQuality.totalVideoFrames' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`totalVideoFrames`

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

-   The [`HTMLVideoElement.getVideoPlaybackQuality()`](../htmlvideoelement/getvideoplaybackquality) method for constructing and returning this interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/totalVideoFrames" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/totalVideoFrames</a>

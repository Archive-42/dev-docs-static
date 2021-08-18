VideoPlaybackQuality.corruptedVideoFrames
=========================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`VideoPlaybackQuality`](../videoplaybackquality) interface's read-only `corruptedVideoFrames` property the number of corrupted video frames that have been received since the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element was last loaded or reloaded.

Syntax
------

    corruptFrameFount = videoPlaybackQuality.corruptedVideoFrames;

### Value

The number of corrupted video frames that have been received since the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element was last loaded or reloaded.

It is up to the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to determine whether or not to display a corrupted video frame. If a corrupted frame is dropped, then both `corruptedVideoFrames` and [`droppedVideoFrames`](droppedvideoframes) are incremented.

Example
-------

This example determines the percentage of frames which have been corrupted, and if the value is greater than 5%, calls a funciton called `downgradeVideo()` that would be implemented to switch to a different video that might tax the network less.

    var videoElem = document.getElementById("my_vid");
    var quality = videoElem.getVideoPlaybackQuality();

    if (quality.corruptedVideoFrames/quality.totalVideoFrames > 0.05) {
      downgradeVideo(videoElem);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-playback-quality/#dom-videoplaybackquality-corruptedvideoframes">Media Playback Quality<br />
<span class="small">The definition of 'VideoPlaybackQuality: corruptedVideoFrames' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr></tbody></table>

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

`corruptedVideoFrames`

80

12

42-73

11

Only works on Windows 8+.

67

8

80

80

No

No

No

13.0

See also
--------

-   The [`HTMLVideoElement.getVideoPlaybackQuality()`](../htmlvideoelement/getvideoplaybackquality) method for constructing and returning this interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/corruptedVideoFrames" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/corruptedVideoFrames</a>

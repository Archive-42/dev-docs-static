VideoPlaybackQuality.droppedVideoFrames
=======================================

  
The read-only `droppedVideoFrames` property of the [`VideoPlaybackQuality`](../videoplaybackquality) interface returns the number of video frames which have been dropped rather than being displayed since the last time the media was loaded into the [`HTMLVideoElement`](../htmlvideoelement).

Syntax
------

    value = videoPlaybackQuality.droppedVideoFrames;

### Value

An unsigned 64-bit value indicating the number of frames that have been dropped since the last time the media in the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element was loaded or reloaded. This information can be used to determine whether or not to downgrade the video stream to avoid dropping frames.

Frames are typically dropped either before or after decoding them, when it's determined that it will not be possible to draw them to the screen at the correct time.

Example
-------

This example calls [`getVideoPlaybackQuality()`](../htmlvideoelement/getvideoplaybackquality) to obtain a [`VideoPlaybackQuality`](../videoplaybackquality) object, then determines what percentage of frames have been dropped. That value is then presented in an element for the user's reference.

    var videoElem = document.getElementById("my_vid");
    var percentElem = document.getElementById("percent");
    var quality = videoElem.getVideoPlaybackQuality();

    var dropPercent = (quality.droppedVideoFrames/quality.totalVideoFrames)*100;
    percentElem.innerText = Math.trunc(dropPercent).toString(10);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-playback-quality/#videoplaybackquality-interface">Media Playback Quality<br />
<span class="small">The definition of 'VideoPlaybackQuality.droppedVideoFrames' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`droppedVideoFrames`

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

-   The [`HTMLVideoElement.getVideoPlaybackQuality()`](../htmlvideoelement/getvideoplaybackquality) method, which creates and returns `VideoPlaybackQuality` objects

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/droppedVideoFrames" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality/droppedVideoFrames</a>

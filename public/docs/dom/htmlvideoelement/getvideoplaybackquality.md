# HTMLVideoElement.getVideoPlaybackQuality()

The **[`HTMLVideoElement`](../htmlvideoelement)** method `getVideoPlaybackQuality()` creates and returns a [`VideoPlaybackQuality`](../videoplaybackquality) object containing metrics including how many frames have been lost.

The data returned can be used to evaluate the quality of the video stream.

## Syntax

    videoPQ = videoElement.getVideoPlaybackQuality();

### Return value

A [`VideoPlaybackQuality`](../videoplaybackquality) object providing information about the video element's current playback quality.

## Example

This example updates an element to indicate the total number of video frames that have elapsed so far in the playback process. This value includes any dropped or corrupted frames, so it's not the same as "total number of frames played."

    var videoElem = document.getElementById("my_vid");
    var counterElem = document.getElementById("counter");
    var quality = videoElem.getVideoPlaybackQuality();

    counterElem.innerText = quality.totalVideoFrames;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-playback-quality/#dom-htmlvideoelement-getvideoplaybackquality">Media Playback Quality<br />
<span class="small">The definition of 'HTMLVideoElement.getVideoPlaybackQuality()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`getVideoPlaybackQuality`

80

12

42

11

Only works on Windows 8+.

67

8

80

80

42

57

8

13.0

## See also

- The [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element
- The [`VideoPlaybackQuality`](../videoplaybackquality) interface.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/getVideoPlaybackQuality" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/getVideoPlaybackQuality</a>

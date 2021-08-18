VideoPlaybackQuality
====================

A `VideoPlaybackQuality` object is returned by the [`HTMLVideoElement.getVideoPlaybackQuality()`](htmlvideoelement/getvideoplaybackquality) method and contains metrics that can be used to determine the playback quality of a video.

Properties
----------

*The `VideoPlaybackQuality` interface doesn't inherit properties from any other interfaces.*

 [`creationTime`](videoplaybackquality/creationtime) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) containing the time in milliseconds between the start of the navigation and the creation of the object.

 [`droppedVideoFrames`](videoplaybackquality/droppedvideoframes) <span class="badge inline readonly">Read only </span>   
An `unsigned long` giving the number of video frames dropped since the creation of the associated [`HTMLVideoElement`](htmlvideoelement).

 [`totalVideoFrames`](videoplaybackquality/totalvideoframes) <span class="badge inline readonly">Read only </span>   
An `unsigned long` giving the number of video frames created and dropped since the creation of the associated [`HTMLVideoElement`](htmlvideoelement).

### Obsolete properties

 [`corruptedVideoFrames`](videoplaybackquality/corruptedvideoframes) <span class="badge inline readonly">Read only </span>   
An `unsigned long` giving the number of video frames corrupted since the creation of the associated [`HTMLVideoElement`](htmlvideoelement). A corrupted frame may be created or dropped.

 [`totalFrameDelay`](videoplaybackquality/totalframedelay) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A `double` containing the sum of the frame delay since the creation of the associated [`HTMLVideoElement`](htmlvideoelement). The frame delay is the difference between a frame's theoretical presentation time and its effective display time.

Methods
-------

*The `VideoPlaybackQuality` interface has no methods, and does not inherit any.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-playback-quality/#idl-def-videoplaybackquality">Media Playback Quality<br />
<span class="small">The definition of 'VideoPlaybackQuality' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`VideoPlaybackQuality`

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

-   The [`HTMLVideoElement.getVideoPlaybackQuality()`](htmlvideoelement/getvideoplaybackquality) method to get a `VideoPlaybackQuality` object
-   [`MediaSource`](mediasource)
-   [`SourceBuffer`](sourcebuffer)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoPlaybackQuality</a>

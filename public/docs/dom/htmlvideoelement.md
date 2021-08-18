HTMLVideoElement
================

The `HTMLVideoElement` interface provides special properties and methods for manipulating video objects. It also inherits properties and methods of [`HTMLMediaElement`](htmlmediaelement) and [`HTMLElement`](htmlelement).

The list of [supported media formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats) varies from one browser to the other. You should either provide your video in a single format that all the relevant browsers supports, or provide multiple video sources in enough different formats that all the browsers you need to support are covered.

Properties
----------

*Inherits properties from its ancestor interfaces, [`HTMLMediaElement`](htmlmediaelement), and [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLVideoElement.height`</span>  
Is a [`DOMString`](domstring) that reflects the [`height`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-height) HTML attribute, which specifies the height of the display area, in CSS pixels.

<span class="page-not-created">`HTMLVideoElement.poster`</span>  
Is a [`DOMString`](domstring) that reflects the [`poster`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-poster) HTML attribute, which specifies an image to show while no video data is available.

 [`HTMLVideoElement.videoHeight`](htmlvideoelement/videoheight) <span class="badge inline readonly">Read only </span>   
Returns an unsigned integer value indicating the intrinsic height of the resource in CSS pixels, or 0 if no media is available yet.

 [`HTMLVideoElement.videoWidth`](htmlvideoelement/videowidth) <span class="badge inline readonly">Read only </span>   
Returns an unsigned integer value indicating the intrinsic width of the resource in CSS pixels, or 0 if no media is available yet.

<span class="page-not-created">`HTMLVideoElement.width`</span>  
Is a [`DOMString`](domstring) that reflects the [`width`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-width) HTML attribute, which specifies the width of the display area, in CSS pixels.

[`HTMLVideoElement.autoPictureInPicture`](htmlvideoelement/autopictureinpicture)  
The `autoPictureInPicture` attribute will automatically enter and leave the picture-in-picture mode for a video element when the user switches tab and/or applications

[`HTMLVideoElement.disablePictureInPicture`](htmlvideoelement/disablepictureinpicture)  
The `disablePictureInPicture` property will hint the user agent to not suggest the picture-in-picture to users or to request it automatically

### Gecko-specific properties

 <span class="page-not-created">`HTMLVideoElement.mozParsedFrames`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns an `unsigned long` with the count of video frames that have been parsed from the media resource.

 <span class="page-not-created">`HTMLVideoElement.mozDecodedFrames`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns an `unsigned long` with the count of parsed video frames that have been decoded into images.

 <span class="page-not-created">`HTMLVideoElement.mozPresentedFrames`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns an `unsigned long` with the count of decoded frames that have been presented to the rendering pipeline for painting.

 <span class="page-not-created">`HTMLVideoElement.mozPaintedFrames`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns an `unsigned long` with the count of presented frames which were painted on the screen.

 <span class="page-not-created">`HTMLVideoElement.mozFrameDelay`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns an `double` with the time which the last painted video frame was late by, in seconds.

 <span class="page-not-created">`HTMLVideoElement.mozHasAudio`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns a [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if there is some audio associated with the video.

### Microsoft Extensions

 [`HTMLVideoElement.msFrameStep()`](htmlvideoelement/msframestep) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Steps the video by one frame forward or one frame backward.

 [`HTMLVideoElement.msHorizontalMirror`](htmlvideoelement/mshorizontalmirror) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Gets or sets whether a video element is flipped horizontally in the display.

 [`HTMLVideoElement.msInsertVideoEffect()`](htmlvideoelement/msinsertvideoeffect) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Inserts the specified video effect into the media pipeline.

 [`HTMLVideoElement.msIsLayoutOptimalForPlayback`](htmlvideoelement/msislayoutoptimalforplayback) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span>   
Indicates whether the video can be rendered more efficiently.

 [`HTMLVideoElement.msIsStereo3D`](htmlvideoelement/msisstereo3d) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span>   
Determines whether the system considers the loaded video source to be stereo 3-D or not. Value set to true indicates source is stereo 3D.

 [`HTMLVideoElement.msZoom`](htmlvideoelement/mszoom) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Controls whether the video frame is trimmed to fit the video display.

Methods
-------

*Inherits methods from its parent, [`HTMLMediaElement`](htmlmediaelement), and from its ancestor [`HTMLElement`](htmlelement).*

 [`HTMLVideoElement.getVideoPlaybackQuality()`](htmlvideoelement/getvideoplaybackquality) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a [`VideoPlaybackQuality`](videoplaybackquality) object that contains the current playback metrics. This information includes things like the number of dropped or corrupted frames, as well as the total number of frames.

[`HTMLVideoElement.requestPictureInPicture()`](htmlvideoelement/requestpictureinpicture)  
Requests that the user agent make video enters picture-in-picture mode

Events
------

*Inherits events from its parent, [`HTMLMediaElement`](htmlmediaelement), and from its ancestor [`HTMLElement`](htmlelement).* Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`enterpictureinpicture`](htmlvideoelement/enterpictureinpicture_event)  
Sent to a [`HTMLVideoElement`](htmlvideoelement) when it enters Picture-in-Picture mode. The associated event handler is [`HTMLVideoElement.onenterpictureinpicture`](htmlvideoelement/onenterpictureinpicture)

[`leavepictureinpicture`](htmlvideoelement/leavepictureinpicture_event)  
Sent to a [`HTMLVideoElement`](htmlvideoelement) when it leaves Picture-in-Picture mode. The associated event handler is [`HTMLVideoElement.onleavepictureinpicture`](htmlvideoelement/onleavepictureinpicture)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlvideoelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLVideoElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`HTMLVideoElement`

1

12

3.5

9

10.5

3.1

1

18

4

11

2

1.0

`autoPictureInPicture`

No

No

No

No

No

13.1

No

No

No

No

13.4

No

`cancelVideoFrameCallback`

83

83

No

No

69

No

83

83

No

59

No

13.0

`disablePictureInPicture`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

`enterpictureinpicture_event`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

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

`height`

1

12

3.5

9

10.5

3.1

1

18

4

11

2

1.0

`leavepictureinpicture_event`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

`mozDecodedFrames`

No

No

5

No

No

No

No

No

5

No

No

No

`mozFrameDelay`

No

No

5

No

No

No

No

No

5

No

No

No

`mozHasAudio`

No

No

15

No

No

No

No

No

15

No

No

No

`mozPaintedFrames`

No

No

5

No

No

No

No

No

5

No

No

No

`mozParsedFrames`

No

No

5

No

No

No

No

No

5

No

No

No

`mozPresentedFrames`

No

No

5

No

No

No

No

No

5

No

No

No

`msIsStereo3D`

No

12-79

No

10

No

No

No

No

No

No

No

No

`onenterpictureinpicture`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

`onleavepictureinpicture`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

`playsInline`

75

79

No

No

62

10

75

75

No

54

10

11.0

`poster`

1

12

3.6

9

10.5

3.1

1

18

4

11

2

1.0

`requestPictureInPicture`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

`requestVideoFrameCallback`

83

83

No

No

69

No

83

83

No

59

No

13.0

`videoHeight`

1

12

3.5

9

10.5

3.1

1

18

4

11

2

1.0

`videoWidth`

1

12

3.5

9

10.5

3.1

1

18

4

11

2

1.0

`width`

1

12

3.5

9

10.5

3.1

1

18

4

11

2

1.0

See also
--------

-   HTML element implementing this interface: [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video).
-   [Demo of video paint statistics](https://people.mozilla.org/~cpearce/paint-stats-demo.html)
-   [Supported media formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement</a>

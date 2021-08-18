Media Source API
================

**Draft**

This page is not complete.

The **Media Source API**, formally known as **Media Source Extensions** (**MSE**), provides functionality enabling plugin-free web-based streaming media. Using MSE, media streams can be created via JavaScript, and played using [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements.

Media Source Extensions concepts and usage
------------------------------------------

Playing video and audio has been available in web applications without plugins for a few years now, but the basic features offered have really only been useful for playing single whole tracks. We can't, for example, combine/split arraybuffers. Streaming media has up until recently been the domain of Flash, with technologies like Flash Media Server serving video streams using the RTMP protocol.

### The MSE standard

With Media Source Extensions (MSE), this is changing. MSE allows us to replace the usual single track `src` value fed to media elements with a reference to a `MediaSource` object, which is a container for information like the ready state of the media for being played, and references to multiple `SourceBuffer` objects that represent the different chunks of media that make up the entire stream. MSE gives us finer grained control over how much and how often content is fetched, and some control over memory usage details, such as when buffers are evicted. It lays the groundwork for adaptive bitrate streaming clients (such as those using DASH or HLS) to be built on its extensible API.

Creating assets that work with MSE in modern browsers is a laborious process, taking significant time, computing power, and energy. The usage of external utilities to massage the content into a suitable format is required. While browser support for the various media containers with MSE is spotty, usage of the H.264 video codec, AAC audio codec, and MP4 container format is a common baseline. MSE also provides an API for runtime detection of container and codec support.

If you do not require explicit control of video quality over time, the rate at which content is fetched, or the rate at which memory is evicted, then the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) and [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) tags may well be a simple and adequate solution.

### DASH

Dynamic Adaptive Streaming over HTTP (DASH) is a protocol for specifying how adaptive content should be fetched. It is effectively a layer built on top of MSE for building adaptive bitrate streaming clients. While there are other protocols available (such as HTTP Live Streaming (HLS)), DASH has the most platform support.

DASH moves lots of logic out of the network protocol and into the client side application logic, using the simpler HTTP protocol to fetch files. Indeed, one can support DASH with a simple static file server, which is also great for CDNs. This is in direct contrast with previous streaming solutions that required expensive licenses for proprietary non-standard client/server protocol implementations.

The two most common use cases for DASH involve watching content “on demand” or “live.” On demand allows a developer to take their time transcoding the assets into multiple resolutions of various quality.

Live profile content can introduce latency due to its transcoding and broadcasting, so DASH is not suitable for real time communication like [WebRTC](webrtc_api) is. It can however support significantly more client connections than WebRTC.

There are numerous available free and open source tools for transcoding content and preparing it for use with DASH, DASH file servers, and DASH client libraries written in JavaScript.

Interfaces
----------

[`MediaSource`](mediasource)  
Represents a media source to be played via an [`HTMLMediaElement`](htmlmediaelement) object.

[`SourceBuffer`](sourcebuffer)  
Represents a chunk of media to be passed into an [`HTMLMediaElement`](htmlmediaelement) via a `MediaSource` object.

[`SourceBufferList`](sourcebufferlist)  
A simple container list for multiple `SourceBuffer` objects.

[`VideoPlaybackQuality`](videoplaybackquality)  
Contains information about the quality of video being played by a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, such as number of dropped or corrupted frames. Returned by the [`HTMLVideoElement.getVideoPlaybackQuality()`](htmlvideoelement/getvideoplaybackquality) method.

[`TrackDefault`](trackdefault)  
Provides a [`SourceBuffer`](sourcebuffer) with kind, label, and language information for tracks that do not contain this information in the [initialization segments](https://w3c.github.io/media-source/#init-segment) of a media chunk.

[`TrackDefaultList`](trackdefaultlist)  
A simple container list for multiple `TrackDefault` objects.

Extensions to other interfaces
------------------------------

[`URL.createObjectURL()`](url/createobjecturl)  
Creates an object URL pointing to a `MediaSource` object that can then be specified as the `src` value of an HTML media element to play a media stream.

[`HTMLMediaElement.seekable`](htmlmediaelement/seekable)  
When a `MediaSource` object is played by an HTML media element, this property will return a [`TimeRanges`](timeranges) object that contains the time ranges that the user is able to seek to.

[`HTMLVideoElement.getVideoPlaybackQuality()`](htmlvideoelement/getvideoplaybackquality)  
Returns a [`VideoPlaybackQuality`](videoplaybackquality) object for the currently played video.

 [`AudioTrack.sourceBuffer`](audiotrack/sourcebuffer), [`VideoTrack.sourceBuffer`](videotrack/sourcebuffer), <span class="page-not-created">`TextTrack.sourceBuffer`</span>   
Returns the [`SourceBuffer`](sourcebuffer) that created the track in question.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/">Media Source Extensions</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Media_Source_Extensions_API`

31

23-31

12

42

11

18

15-18

8

4.4.3

31

25-31

41

18

14-18

8

2.0

1.5-2.0

`MediaSource`

31

23-31

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

41

14

No

2.0

`activeSourceBuffers`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

41

14

No

1.5

`addSourceBuffer`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

41

14

No

1.5

`clearLiveSeekableRange`

62

17

No

No

49

10

62

62

?

46

No

8.0

`duration`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

41

14

No

1.5

`endOfStream`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

41

14

No

1.5

`isTypeSupported`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

41

14

8

1.5

`onsourceclose`

53

17

No

This event handler attribute is not supported; however, the event itself is supported since Firefox 42. The event can be listened to via `mediaSource.addEventListener('sourceclose', function() {});`. See [bug 1689222](https://bugzil.la/1689222).

11

Only works on Windows 8+.

15

10.1

4.4.3

33

No

This event handler attribute is not supported; however, the event itself is supported since Firefox 42. The event can be listened to via `mediaSource.addEventListener('sourceclose', function() {});`. See [bug 1689222](https://bugzil.la/1689222).

14

No

2.0

`onsourceended`

53

17

42

11

Only works on Windows 8+.

15

10.1

4.4.3

33

41

14

No

2.0

`onsourceopen`

53

17

42

11

Only works on Windows 8+.

15

10.1

4.4.3

33

41

14

No

2.0

`readyState`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

41

14

No

2.0

`removeSourceBuffer`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

41

14

No

1.5

`setLiveSeekableRange`

62

17

No

No

49

10.1

62

62

?

46

No

8.0

`sourceBuffers`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

41

14

No

1.5

See also
--------

-   [Transcoding assets for Media Source Extensions](media_source_extensions_api/transcoding_assets_for_mse)
-   Using MSE to create a basic streaming service (TBD)
-   Using MPEG DASH to create a streaming application (TBD)
-   The [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements.
-   [`HTMLMediaElement`](htmlmediaelement), [`HTMLVideoElement`](htmlvideoelement), [`HTMLAudioElement`](htmlaudioelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Media_Source_Extensions_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Media_Source_Extensions_API</a>

SourceBuffer
============

The `SourceBuffer` interface represents a chunk of media to be passed into an [`HTMLMediaElement`](htmlmediaelement) and played, via a [`MediaSource`](mediasource) object. This can be made up of one or several media segments.

Properties
----------

[`SourceBuffer.appendWindowEnd`](sourcebuffer/appendwindowend)  
Controls the timestamp for the end of the append window.

[`SourceBuffer.appendWindowStart`](sourcebuffer/appendwindowstart)  
Controls the timestamp for the start of the [append window](https://w3c.github.io/media-source/#append-window). This is a timestamp range that can be used to filter what media data is appended to the `SourceBuffer`. Coded media frames with timestamps within this range will be appended, whereas those outside the range will be filtered out.

 [`SourceBuffer.audioTracks`](sourcebuffer/audiotracks) <span class="badge inline readonly">Read only </span>   
A list of the audio tracks currently contained inside the `SourceBuffer`.

 [`SourceBuffer.buffered`](sourcebuffer/buffered) <span class="badge inline readonly">Read only </span>   
Returns the time ranges that are currently buffered in the `SourceBuffer`.

[`SourceBuffer.mode`](sourcebuffer/mode)  
Controls how the order of media segments in the `SourceBuffer` is handled, in terms of whether they can be appended in any order, or they have to be kept in a strict sequence.

 [`SourceBuffer.textTracks`](sourcebuffer/texttracks) <span class="badge inline readonly">Read only </span>   
A list of the text tracks currently contained inside the `SourceBuffer`.

[`SourceBuffer.timestampOffset`](sourcebuffer/timestampoffset)  
Controls the offset applied to timestamps inside media segments that are subsequently appended to the `SourceBuffer`.

[`SourceBuffer.trackDefaults`](sourcebuffer/trackdefaults)  
Specifies the default values to use if kind, label, and/or language information is not available in the [initialization segment](https://w3c.github.io/media-source/#init-segment) of the media to be appended to the `SourceBuffer`.

 [`SourceBuffer.updating`](sourcebuffer/updating) <span class="badge inline readonly">Read only </span>   
A boolean indicating whether the `SourceBuffer` is currently being updated — i.e. whether an [`SourceBuffer.appendBuffer()`](sourcebuffer/appendbuffer), [`SourceBuffer.appendStream()`](sourcebuffer/appendstream), or [`SourceBuffer.remove()`](sourcebuffer/remove) operation is currently in progress.

 [`SourceBuffer.videoTracks`](sourcebuffer/videotracks) <span class="badge inline readonly">Read only </span>   
A list of the video tracks currently contained inside the `SourceBuffer`.

### Event handlers

<span class="page-not-created">`SourceBuffer.onabort`</span>  
Fired whenever [`SourceBuffer.appendBuffer()`](sourcebuffer/appendbuffer) or [`SourceBuffer.appendStream()`](sourcebuffer/appendstream) is ended by a call to [`SourceBuffer.abort()`](sourcebuffer/abort). [`SourceBuffer.updating`](sourcebuffer/updating) changes from `true` to `false`.

<span class="page-not-created">`SourceBuffer.onerror`</span>  
Fired whenever an error occurs during [`SourceBuffer.appendBuffer()`](sourcebuffer/appendbuffer) or [`SourceBuffer.appendStream()`](sourcebuffer/appendstream). [`SourceBuffer.updating`](sourcebuffer/updating) changes from `true` to `false`.

<span class="page-not-created">`SourceBuffer.onupdate`</span>  
Fired whenever [`SourceBuffer.appendBuffer()`](sourcebuffer/appendbuffer) method or the [`SourceBuffer.remove()`](sourcebuffer/remove) completes. [`SourceBuffer.updating`](sourcebuffer/updating) changes from `true` to `false`. This event is fired before `onupdateend`.

<span class="page-not-created">`SourceBuffer.onupdateend`</span>  
Fired whenever [`SourceBuffer.appendBuffer()`](sourcebuffer/appendbuffer) method or the [`SourceBuffer.remove()`](sourcebuffer/remove) has ended. This event is fired after `onupdate`.

<span class="page-not-created">`SourceBuffer.onupdatestart`</span>  
Fired whenever the value of [`SourceBuffer.updating`](sourcebuffer/updating) transitions from `false` to `true`.

Methods
-------

*Inherits methods from its parent interface, [`EventTarget`](eventtarget).*

[`SourceBuffer.abort()`](sourcebuffer/abort)  
Aborts the current segment and resets the segment parser.

[`SourceBuffer.appendBuffer()`](sourcebuffer/appendbuffer)  
Appends media segment data from an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or [`ArrayBufferView`](arraybufferview) object to the `SourceBuffer`.

 [`SourceBuffer.appendBufferAsync()`](sourcebuffer/appendbufferasync) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Starts the process of asynchronously appending the specified buffer to the `SourceBuffer`. Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the buffer has been appended.

[`SourceBuffer.appendStream()`](sourcebuffer/appendstream)  
Appends media segment data from a `ReadableStream` object to the `SourceBuffer`.

[`SourceBuffer.changeType()`](sourcebuffer/changetype)  
Changes the [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) that future calls to [`appendBuffer()`](sourcebuffer/appendbuffer) will expect the new data to conform to.

[`SourceBuffer.remove()`](sourcebuffer/remove)  
Removes media segments within a specific time range from the `SourceBuffer`.

 [`SourceBuffer.removeAsync()`](sourcebuffer/removeasync) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Starts the process of asynchronously removing media segments in the specified range from the `SourceBuffer`. Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once all matching segments have been removed.

Examples
--------

The following simple example loads a video chunk by chunk as fast as possible, playing it as soon as it can. This example was written by Nick Desaulniers and can be [viewed live here](https://nickdesaulniers.github.io/netfix/demo/bufferAll.html) (you can also [download the source](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferAll.html) for further investigation.)

    var video = document.querySelector('video');

    var assetURL = 'frag_bunny.mp4';
    // Need to be specific for Blink regarding codecs
    // ./mp4info frag_bunny.mp4 | grep Codec
    var mimeCodec = 'video/mp4; codecs="avc1.42E01E, mp4a.40.2"';

    if ('MediaSource' in window && MediaSource.isTypeSupported(mimeCodec)) {
      var mediaSource = new MediaSource();
      //console.log(mediaSource.readyState); // closed
      video.src = URL.createObjectURL(mediaSource);
      mediaSource.addEventListener('sourceopen', sourceOpen);
    } else {
      console.error('Unsupported MIME type or codec: ', mimeCodec);
    }

    function sourceOpen (_) {
      //console.log(this.readyState); // open
      var mediaSource = this;
      var sourceBuffer = mediaSource.addSourceBuffer(mimeCodec);
      fetchAB(assetURL, function (buf) {
        sourceBuffer.addEventListener('updateend', function (_) {
          mediaSource.endOfStream();
          video.play();
          //console.log(mediaSource.readyState); // ended
        });
        sourceBuffer.appendBuffer(buf);
      });
    }

    function fetchAB (url, cb) {
      console.log(url);
      var xhr = new XMLHttpRequest;
      xhr.open('get', url);
      xhr.responseType = 'arraybuffer';
      xhr.onload = function () {
        cb(xhr.response);
      };
      xhr.send();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#sourcebuffer">Media Source Extensions<br />
<span class="small">The definition of 'SourceBuffer' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`SourceBuffer`

31

23-31

12

42

11

Only works on Windows 8+.

18

15-18

8

4.4.3

31

25-31

No

18

14-18

13

Exposed in Mobile Safari on iPad but not on iPhone.

3.0

2.0-3.0

`abort`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

25

No

14

No

2.0

`appendBuffer`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

`appendBufferAsync`

No

No

62

No

No

No

No

Yes

No

No

No

Yes

`appendStream`

No

12-79

No

?

No

?

?

?

No

?

No

?

`appendWindowEnd`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

`appendWindowStart`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

`audioTracks`

51

79

12-79

No

11

Only works on Windows 8+.

38

8

No

51

No

41

13

Exposed in Mobile Safari on iPad but not on iPhone.

No

`buffered`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

`changeType`

70

79

63

?

?

?

70

70

No

?

No

10.0

`mode`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

`onabort`

53

17

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

`onerror`

53

17

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

`onupdate`

53

17

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

`onupdateend`

53

17

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

`onupdatestart`

53

17

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

`remove`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

`removeAsync`

No

No

62

No

No

No

No

Yes

No

No

No

Yes

`textTracks`

No

18

No

No

No

8

No

No

No

No

13

Exposed in Mobile Safari on iPad but not on iPhone.

No

`timestampOffset`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

`trackDefaults`

?

?

No

?

?

?

?

?

No

?

No

?

`updating`

23

12

42

11

Only works on Windows 8+.

15

8

4.4.3

33

No

14

No

3.0

`videoTracks`

51

79

12-79

No

11

Only works on Windows 8+.

38

8

No

51

No

41

13

Exposed in Mobile Safari on iPad but not on iPhone.

No

See also
--------

-   [`MediaSource`](mediasource)
-   [`SourceBufferList`](sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer</a>

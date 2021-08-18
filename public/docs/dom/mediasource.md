MediaSource
===========

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MediaSource` interface of the [Media Source Extensions API](media_source_extensions_api) represents a source of media data for an [`HTMLMediaElement`](htmlmediaelement) object. A `MediaSource` object can be attached to a [`HTMLMediaElement`](htmlmediaelement) to be played in the user agent.

Constructor
-----------

[`MediaSource()`](mediasource/mediasource)  
Constructs and returns a new `MediaSource` object with no associated source buffers.

Properties
----------

 [`MediaSource.sourceBuffers`](mediasource/sourcebuffers) <span class="badge inline readonly">Read only </span>   
Returns a [`SourceBufferList`](sourcebufferlist) object containing the list of [`SourceBuffer`](sourcebuffer) objects associated with this `MediaSource`.

 [`MediaSource.activeSourceBuffers`](mediasource/activesourcebuffers) <span class="badge inline readonly">Read only </span>   
Returns a [`SourceBufferList`](sourcebufferlist) object containing a subset of the [`SourceBuffer`](sourcebuffer) objects contained within [`MediaSource.sourceBuffers`](mediasource/sourcebuffers) — the list of objects providing the selected video track, enabled audio tracks, and shown/hidden text tracks.

 [`MediaSource.readyState`](mediasource/readystate) <span class="badge inline readonly">Read only </span>   
Returns an enum representing the state of the current `MediaSource`, whether it is not currently attached to a media element (`closed`), attached and ready to receive [`SourceBuffer`](sourcebuffer) objects (`open`), or attached but the stream has been ended via [`MediaSource.endOfStream()`](mediasource/endofstream) (`ended`.)

[`MediaSource.duration`](mediasource/duration)  
Gets and sets the duration of the current media being presented.

### Event handlers

<span class="page-not-created">`MediaSource.onsourceclose`</span>  
The event handler for the `sourceclose` event.

<span class="page-not-created">`MediaSource.onsourceended`</span>  
The event handler for the `sourceended` event.

<span class="page-not-created">`MediaSource.onsourceopen`</span>  
The event handler for the `sourceopen` event.

Methods
-------

*Inherits methods from its parent interface, [`EventTarget`](eventtarget).*

[`MediaSource.addSourceBuffer()`](mediasource/addsourcebuffer)  
Creates a new [`SourceBuffer`](sourcebuffer) of the given MIME type and adds it to the [`MediaSource.sourceBuffers`](mediasource/sourcebuffers) list.

[`MediaSource.clearLiveSeekableRange()`](mediasource/clearliveseekablerange)  
Clears a seekable range previously set with a call to `setLiveSeekableRange()`.

[`MediaSource.endOfStream()`](mediasource/endofstream)  
Signals the end of the stream.

[`MediaSource.removeSourceBuffer()`](mediasource/removesourcebuffer)  
Removes the given [`SourceBuffer`](sourcebuffer) from the [`MediaSource.sourceBuffers`](mediasource/sourcebuffers) list.

[`MediaSource.setLiveSeekableRange()`](mediasource/setliveseekablerange)  
Sets the range that the user can seek to in the media element.

Static methods
--------------

[`MediaSource.isTypeSupported()`](mediasource/istypesupported)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating if the given MIME type is supported by the current user agent — this is, if it can successfully create [`SourceBuffer`](sourcebuffer) objects for that MIME type.

Examples
--------

The following simple example loads a video with [`XMLHttpRequest`](xmlhttprequest), playing it as soon as it can. This example was written by Nick Desaulniers and can be [viewed live here](https://nickdesaulniers.github.io/netfix/demo/bufferAll.html) (you can also [download the source](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferAll.html) for further investigation.)

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
    };

    function fetchAB (url, cb) {
      console.log(url);
      var xhr = new XMLHttpRequest;
      xhr.open('get', url);
      xhr.responseType = 'arraybuffer';
      xhr.onload = function () {
        cb(xhr.response);
      };
      xhr.send();
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#mediasource">Media Source Extensions<br />
<span class="small">The definition of 'MediaSource' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaSource`

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

-   [`SourceBuffer`](sourcebuffer)
-   [`SourceBufferList`](sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource</a>

MediaSource.readyState
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `readyState` read-only property of the [`MediaSource`](../mediasource) interface returns an enum representing the state of the current `MediaSource`. The three possible values are:

-   `closed`: The source is not currently attached to a media element.
-   `open`: The source is attached to a media element and ready to receive [`SourceBuffer`](../sourcebuffer) objects.
-   `ended`: The source is attached to a media element but the stream has been ended via a call to [`MediaSource.endOfStream()`](endofstream).

Syntax
------

    var myReadyState = mediaSource.readyState;

### Value

A [`DOMString`](../domstring).

Example
-------

The following snippet is from a simple example written by Nick Desaulniers ([view the full demo live](https://nickdesaulniers.github.io/netfix/demo/bufferAll.html), or [download the source](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferAll.html) for further investigation.)

    if ('MediaSource' in window && MediaSource.isTypeSupported(mimeCodec)) {
      var mediaSource = new MediaSource;
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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-mediasource-readystate">Media Source Extensions<br />
<span class="small">The definition of 'readyState' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`SourceBuffer`](../sourcebuffer)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/readyState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/readyState</a>

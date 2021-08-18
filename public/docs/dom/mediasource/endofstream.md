MediaSource.endOfStream()
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `endOfStream()` method of the [`MediaSource`](../mediasource) interface signals the end of the stream.

Syntax
------

    mediaSource.endOfStream(endOfStreamError);

### Parameters

endOfStreamError <span class="badge inline optional">Optional</span>   
A [`DOMString`](../domstring) representing an error to throw when the end of the stream is reached. The possible values are:

-   `network`: Terminates playback and signals that a network error has occurred. This can be used create a custom error handler related to media streams. For example, you might have a function that handles media chunk requests, separate from other network requests. When you make an [XMLHttpRequest](../xmlhttprequest) call for a media chunk, and `onabort` or `onerror` triggers, you might want to call `endOfStream('network')`, display a descriptive message in the UI, and maybe retry the network request immediately or wait until the network is back up (via some kind of polling.)
-   `decode`: Terminates playback and signals that a decoding error has occurred. This can be used to indicate that a parsing error has occurred while fetching media data; maybe the data is corrupt, or is encoded using a codec that the browser doesn't know how to decode.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td><a href="readystate"><code>MediaSource.readyState</code></a> is not equal to <code>open</code>, or one or more of the <a href="../sourcebuffer"><code>SourceBuffer</code></a> objects in <a href="sourcebuffers"><code>MediaSource.sourceBuffers</code></a> are being updated (i.e. their <a href="../sourcebuffer/updating"><code>SourceBuffer.updating</code></a> property is <code>true</code>.)</td></tr></tbody></table>

Example
-------

The following snippet is from a simple example written by Nick Desaulniers ([view the full demo live](https://nickdesaulniers.github.io/netfix/demo/bufferAll.html), or [download the source](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferAll.html) for further investigation.)

    var assetURL = 'frag_bunny.mp4';
    // Need to be specific for Blink regarding codecs
    // ./mp4info frag_bunny.mp4 | grep Codec
    var mimeCodec = 'video/mp4; codecs="avc1.42E01E, mp4a.40.2"';

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dom-mediasource-endofstream">Media Source Extensions<br />
<span class="small">The definition of 'endOfStream()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`SourceBuffer`](../sourcebuffer)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/endOfStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/endOfStream</a>

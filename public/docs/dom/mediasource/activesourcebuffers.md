MediaSource.activeSourceBuffers
===============================

The `activeSourceBuffers` read-only property of the [`MediaSource`](../mediasource) interface returns a [`SourceBufferList`](../sourcebufferlist) object containing a subset of the [`SourceBuffer`](../sourcebuffer) objects contained within [`sourceBuffers`](sourcebuffers) — the list of objects providing the selected video track, enabled audio tracks, and shown/hidden text tracks.

Syntax
------

    var myActiveSourceBuffers = mediaSource.activeSourceBuffers;

### Value

A [`SourceBufferList`](../sourcebufferlist) containing the [`SourceBuffer`](../sourcebuffer) objects for each of the active tracks.

Example
-------

The following snippet is based on a simple example written by Nick Desaulniers ([view the full demo live](https://nickdesaulniers.github.io/netfix/demo/bufferAll.html), or [download the source](https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferAll.html) for further investigation.)

    function sourceOpen (_) {
      //console.log(this.readyState); // open
      var mediaSource = this;
      var sourceBuffer = mediaSource.addSourceBuffer(mimeCodec);
      fetchAB(assetURL, function (buf) {
        sourceBuffer.addEventListener('updateend', function (_) {
          mediaSource.endOfStream();
          console.log(mediaSource.activeSourceBuffers);
          // will contain the source buffer that was added above,
          // as it is selected for playing in the video player
          video.play();
          //console.log(mediaSource.readyState); // ended
        });
        sourceBuffer.appendBuffer(buf);
      });
    };

    ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-mediasource-activesourcebuffers">Media Source Extensions<br />
<span class="small">The definition of 'activeSourceBuffers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`SourceBuffer`](../sourcebuffer)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/activeSourceBuffers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/activeSourceBuffers</a>

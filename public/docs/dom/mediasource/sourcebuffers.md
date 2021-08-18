MediaSource.sourceBuffers
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `sourceBuffers` read-only property of the [`MediaSource`](../mediasource) interface returns a [`SourceBufferList`](../sourcebufferlist) object containing the list of [`SourceBuffer`](../sourcebuffer) objects associated with this `MediaSource`.

Syntax
------

    var mySourceBuffers = mediaSource.sourceBuffers;

### Value

A [`SourceBufferList`](../sourcebufferlist).

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
          console.log(mediaSource.sourceBuffers); // will contain the source buffer that was added above
          video.play();
          //console.log(mediaSource.readyState); // ended
        });
        sourceBuffer.appendBuffer(buf);
      });
    };

    ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-mediasource-sourcebuffers">Media Source Extensions<br />
<span class="small">The definition of 'sourceBuffers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

-   [`SourceBuffer`](../sourcebuffer)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/sourceBuffers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/sourceBuffers</a>

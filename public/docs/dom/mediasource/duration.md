MediaSource.duration
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `duration` property of the [`MediaSource`](../mediasource) interface gets and sets the duration of the current media being presented.

Syntax
------

    mediaSource.duration = 5.5; // 5.5 seconds

    var myDuration = mediaSource.duration;

### Value

A double. A value in seconds is expected.

### Exceptions

The following exceptions may be thrown when setting a new value for this property.

<table><thead><tr class="header"><th>Exception</th><th>Explanation</th></tr></thead><tbody><tr class="odd"><td><code>InvalidAccessError</code></td><td>An attempt was made to set a duration value that was negative, or <code>NaN</code>.</td></tr><tr class="even"><td><code>InvalidStateError</code></td><td><a href="readystate"><code>MediaSource.readyState</code></a> is not equal to <code>open</code>, or one or more of the <a href="../sourcebuffer"><code>SourceBuffer</code></a> objects in <a href="sourcebuffers"><code>MediaSource.sourceBuffers</code></a> are being updated (i.e. their <a href="../sourcebuffer/updating"><code>SourceBuffer.updating</code></a> property is <code>true</code>.)</td></tr></tbody></table>

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
          mediaSource.duration = 120;
          video.play();
          //console.log(mediaSource.readyState); // ended
        });
        sourceBuffer.appendBuffer(buf);
      });
    };

    ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-mediasource-duration">Media Source Extensions<br />
<span class="small">The definition of 'duration' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`SourceBuffer`](../sourcebuffer)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/duration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/duration</a>

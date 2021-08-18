SourceBuffer.videoTracks
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `videoTracks` read-only property of the [`SourceBuffer`](../sourcebuffer) interface returns a list of the video tracks currently contained inside the `SourceBuffer`.

Syntax
------

    var myVideoTracks = sourceBuffer.videoTracks;

### Value

An [`VideoTrackList`](../videotracklist) object.

Example
-------

TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#idl-def-sourcebuffer-videotracks">Media Source Extensions<br />
<span class="small">The definition of 'videoTracks' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

-   [`MediaSource`](../mediasource)
-   [`SourceBufferList`](../sourcebufferlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/videoTracks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SourceBuffer/videoTracks</a>

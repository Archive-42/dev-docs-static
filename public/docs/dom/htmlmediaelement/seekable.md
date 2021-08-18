HTMLMediaElement.seekable
=========================

The `seekable` read-only property of [`HTMLMediaElement`](../htmlmediaelement) objects returns a new static [normalized `TimeRanges` object](../timeranges#normalized_timeranges_objects) that represents the ranges of the media resource, if any, that the user agent is able to seek to at the time `seekable` property is accessed.

Syntax
------

    var seekable = audioOrVideo.seekable;

### Value

A new static [normalized TimeRanges object](../timeranges#normalized_timeranges_objects) that represents the ranges of the media resource, if any, that the user agent is able to seek to at the time `seekable` property is accessed.

Examples
--------

    var video = document.querySelector("video");
    var timeRangesObject = video.seekable;
    var timeRanges = [];
    //Go through the object and output an array
    for (let count = 0; count < timeRangesObject.length; count ++) {
        timeRanges.push([timeRangesObject.start(count), timeRangesObject.end(count)]);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/the-video-element.html#dom-media-seekable">HTML Living Standard<br />
<span class="small">The definition of 'seekable' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://w3c.github.io/media-source/#htmlmediaelement-extensions">Media Source Extensions</a></td><td><span class="spec-rec">Recommendation</span></td><td>Specifies a new algorithm for returning the seekable time ranges of a media element whose source is a <a href="../mediasource"><code>MediaSource</code></a> object.</td></tr></tbody></table>

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

`seekable`

43

12

8

9

≤12.1

3.1

Yes

Yes

8

≤12.1

2

Yes

See also
--------

-   The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
-   [Media Source Extensions API](../media_source_extensions_api)
-   [Media buffering, seeking, and time ranges](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/buffering_seeking_time_ranges)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seekable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seekable</a>

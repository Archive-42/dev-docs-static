MediaSource.setLiveSeekableRange()
==================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `setLiveSeekableRange()` method of the [`MediaSource`](../mediasource) interface sets the range that the user can seek to in the media element.

Syntax
------

    mediaSource.setLiveSeekableRange(start, end)

### Parameters

start  
The start of the seekable range to set in seconds measured from the beginning of the source. If the duration of the media source is positive infinity, then the [`TimeRanges`](../timeranges) object returned by the [`HTMLMediaElement.seekable`](../htmlmediaelement/seekable) property will have a start timestamp no greater than this value.

end  
The end of the seekable range to set in seconds measured from the beginning of the source. If the duration of the media source is positive infinity, then the [`TimeRanges`](../timeranges) object returned by the [`HTMLMediaElement.seekable`](../htmlmediaelement/seekable) property will have an end timestamp no less than this value.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

Example
-------

    // TBD

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/media-source/#dom-mediasource-setliveseekablerange">Media Source Extensions<br />
<span class="small">The definition of 'setLiveSeekableRange()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/setLiveSeekableRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSource/setLiveSeekableRange</a>

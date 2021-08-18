HTMLMediaElement.canPlayType()
==============================

The [`HTMLMediaElement`](../htmlmediaelement) method `canPlayType()` reports how likely it is that the current browser will be able to play media of a given MIME type.

**Note:** This feature is not available in [Web Workers](../web_workers_api).

Syntax
------

    canPlayResponse = audioOrVideo.canPlayType(mediaType);

### Parameters

`mediaType`  
A [`DOMString`](../domstring) containing the MIME type of the media.

### Return value

A [`DOMString`](../domstring) indicating how likely it is that the media can be played. The string will be one of the following values:

`probably`  
Media of the type indicated by the `mediaType` parameter is probably playable on this device.

`maybe`  
Not enough information is available to determine for sure whether or not the media will play until playback is actually attempted.

 `""` (empty string)  
Media of the given type definitely can't be played on the current device.

Example
-------

    var obj = document.createElement('video');
    console.log(obj.canPlayType('video/mp4')); // "maybe"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-canplaytype">HTML Living Standard<br />
<span class="small">The definition of 'canplaytype' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.canplaytype' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`canPlayType`

3

12

3.5

Prior to Firefox 28, `canPlayType()` returned `probably` when asked about WebM audio or video files without the `codecs` parameter. Since multiple codecs are supported, this is not enough information to determine if a file can be played, so `maybe` is now correctly returned.

9

≤12.1

4

≤37

18

4

≤12.1

3

1.0

See also
--------

-   The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
-   [`MediaCapabilities`](../mediacapabilities) in the Media Capabilities API
-   [Handling media support issues in web content](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Support_issues)
-   [Guide to media types and formats on the web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/canPlayType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/canPlayType</a>

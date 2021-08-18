HTMLMediaElement.defaultPlaybackRate
====================================

The `HTMLMediaElement.defaultPlaybackRate` property indicates the default playback rate for the media.

Syntax
------

    var dSpeed = video.defaultPlaybackRate;
    audio.defaultPlaybackRate = 1.0;

### Value

A double. 1.0 is "normal speed," values lower than 1.0 make the media play slower than normal, higher values make it play faster. The value 0.0 is invalid and throws a `NOT_SUPPORTED_ERR` exception.

Example
-------

    var obj = document.createElement('video');
    console.log(obj.defaultPlaybackRate); // 1

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-defaultplaybackrate">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.defaultPlaybackRate' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.defaultPlaybackRate' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`defaultPlaybackRate`

43

12

20

9

≤12.1

3.1

43

43

20

≤12.1

2

4.0

See also
--------

-   The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/defaultPlaybackRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/defaultPlaybackRate</a>

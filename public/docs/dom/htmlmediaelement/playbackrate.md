HTMLMediaElement.playbackRate
=============================

The `HTMLMediaElement.playbackRate` property sets the rate at which the media is being played back. This is used to implement user controls for fast forward, slow motion, and so forth. The normal playback rate is multiplied by this value to obtain the current rate, so a value of 1.0 indicates normal speed.

If `playbackRate` is negative, the media is **not** played backwards.

The audio is muted when the fast forward or slow motion is outside a useful range (for example, Gecko mutes the sound outside the range `0.25` to `4.0`).

The pitch of the audio is corrected by default and is the same for every speed. Some browsers implement the non-standard <span class="page-not-created">`HTMLMediaElement.preservesPitch`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> property to control this.

Syntax
------

    // video
    video.playbackRate = 1.5;
    // audio
    audio.playbackRate = 1.0;

### Value

A `double`. `1.0` is "normal speed," values lower than `1.0` make the media play slower than normal, higher values make it play faster. (**Default:** `1.0`)

Example
-------

    var obj = document.createElement('video');
    console.log(obj.playbackRate); // Expected Output: 1

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-playbackrate">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.playbackRate' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.playbackRate' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`playbackRate`

43

12

20

9

≤12.1

3.1

Yes

Yes

20

≤12.1

2

Yes

See also
--------

-   The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/playbackRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/playbackRate</a>

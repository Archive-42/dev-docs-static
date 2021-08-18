HTMLMediaElement.defaultMuted
=============================

The `HTMLMediaElement.defaultMuted` property reflects the [`muted`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-muted) HTML attribute, which indicates whether the media element's audio output should be muted by default. This property has no dynamic effect. To mute and unmute the audio output, use the [`muted`](muted) property.

Syntax
------

    var dMuted = video.defaultMuted;
    audio.defaultMuted = true;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). A value of `true` means that the audio output will be muted by default.

Example
-------

    var videoEle = document.createElement('video');
    videoEle.defaultMuted = true;
    console.log(videoEle.outerHTML); // <video muted=""></video>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-defaultmuted">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.defaultMuted' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.defaultMuted' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`defaultMuted`

15

12

11

No

≤12.1

6

≤37

18

14

≤12.1

6

1.0

See also
--------

-   The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
-   [`HTMLMediaElement.muted`](muted)
-   [`HTMLMediaElement.volume`](volume)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/defaultMuted" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/defaultMuted</a>

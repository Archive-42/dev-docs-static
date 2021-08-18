Videotrack.language
===================

The read-only **[`VideoTrack`](../videotrack)** property `language` returns a string identifying the language used in the video track. For tracks that include multiple languages (such as a movie in English in which a few lines are spoken in other languages), this should be the video's primary language.

Syntax
------

    var videoTrackLanguage = VideoTrack.language;

### Value

A [`DOMString`](../domstring) specifying the BCP 47 ([RFC 5646](https://tools.ietf.org/html/rfc5646)) format language tag of the primary language used in the video track, or an empty string (`""`) if the language is not specified or known, or if the track doesn't contain speech.

For example, if the primary language used in the track is United States English, this value would be `"en-US"`. For Brazilian Portuguese, the value would be `"pt-BR"`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-videotrack-language">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrack: language' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`language`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack/language" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack/language</a>

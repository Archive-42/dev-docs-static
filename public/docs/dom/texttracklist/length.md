TextTrackList.length
====================

The read-only **[`TextTrackList`](../texttracklist)** property `length` returns the number of entries in the `TextTrackList`, each of which is a [`TextTrack`](../texttrack) representing one track in the media element. A value of 0 indicates that there are no text tracks in the media.

Syntax
------

    var trackCount = TextTrackList.length;

### Value

A number indicating how many text tracks are included in the `TextTrackList`. Each track can be accessed by treating the `TextTrackList` as an array of objects of type [`TextTrack`](../texttrack).

Example
-------

This snippet gets the number of text tracks in the first media element found in the [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) by [`querySelector()`](../document/queryselector).

    var mediaElem = document.querySelector("video, audio");
    var numTextTracks = 0;

    if (mediaElem.textTracks) {
      numTextTracks = mediaElem.textTracks.length;
    }

Note that this sample checks to be sure [`HTMLMediaElement.textTracks`](../htmlmediaelement/texttracks) is defined, to avoid failing on browsers without support for [`TextTrack`](../texttrack).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-texttracklist-length">HTML Living Standard<br />
<span class="small">The definition of 'TextTrackList: length' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`length`

44

≤18

Yes

10

31

6

44

44

?

32

7

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackList/length</a>

TextTrackCueList.length
=======================

The `length` read-only property of the [`TextTrackCueList`](../texttrackcuelist) interface returns the number of cues in the list.

Syntax
------

    var length = TextTrackCueList.length;

### Value

An `unsigned long` which is the number of cues in the list.

Examples
--------

The <span class="page-not-created">`TextTrack.cues`</span> property returns a [`TextTrackCueList`](../texttrackcuelist) containing the current cues for that particular track. Calling `cues.length` returns the number of cues in the list. Using the WebVTT track below, the value of `length` is 5.

    WEBVTT

    first
    00:00:00.000 --> 00:00:00.999  line:80%
    Hildy!

    second
    00:00:01.000 --> 00:00:01.499 line:80%
    How are you?

    third
    00:00:01.500 --> 00:00:02.999 line:80%
    Tell me, is the ruler of the universe in?

    fourth
    00:00:03.000 --> 00:00:04.299 line:80%
    Yes, they're in - in a bad humor

    fifth
    00:00:04.300 --> 00:00:06.000 line:80%
    Somebody must've stolen the crown jewels

    let video = document.getElementById("video");
    video.onplay = function () {
      console.log(video.textTracks[0].cues.length) //5;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-texttrackcuelist-length">HTML Living Standard<br />
<span class="small">The definition of 'TextTrackCueList.length' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

23

12

31

10

≤12.1

6

≤37

25

31

≤12.1

6

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList/length</a>

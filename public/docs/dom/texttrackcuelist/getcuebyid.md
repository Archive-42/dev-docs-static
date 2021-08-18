TextTrackCueList.getCueById()
=============================

The `getCueById()` method of the [`TextTrackCueList`](../texttrackcuelist) interface returns the first [`VTTCue`](../vttcue) in the list represented by the `TextTrackCueList` object whose identifier matches the value of `id`.

Syntax
------

    var cue = TextTrackCueList.getCueById(id);

### Parameters

id  
A [`DOMString`](../domstring) which is an identifier for the cue.

### Return value

A [`VTTCue`](../vttcue) object.

Examples
--------

The <span class="page-not-created">`TextTrack.cues`</span> property returns a [`TextTrackCueList`](../texttrackcuelist) containing the current cues for that particular track. Calling `cues.getCueById("second")` returns the [`VTTCue`](../vttcue) with an ID of "second".

    WEBVTT

    first
    00:00:00.000 --> 00:00:00.999  line:80%
    Hildy!

    second
    00:00:01.000 --> 00:00:01.499 line:80%
    How are you?

    let video = document.getElementById("video");
    video.onplay = function () {
      console.log(video.textTracks[0].cues.getCueById("second")) // a VTTCue object;
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

`getCueById`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList/getCueById" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList/getCueById</a>

TextTrackCueList
================

The `TextTrackCueList` interface represents a dynamically updating list of [`TextTrackCue`](texttrackcue) objects.

This interface has no constructor. Retrieve an instance of this object with <span class="page-not-created">`TextTrack.cues`</span> which returns all of the cues in a [`TextTrack`](texttrack) object.

Properties
----------

 [`TextTrackCueList.length`](texttrackcuelist/length)<span class="badge inline readonly">Read only </span>   
An `unsigned long` that is the number of cues in the list.

Methods
-------

[`TextTrackCueList.getCueById()`](texttrackcuelist/getcuebyid)  
Returns the first [`TextTrackCue`](texttrackcue) object with the identifier passed to it.

Examples
--------

The [`HTMLMediaElement.textTracks`](htmlmediaelement/texttracks) property returns a [`TextTrackList`](texttracklist) object listing all of the [`TextTrack`](texttrack) objects, one for each text track linked to the media. The <span class="page-not-created">`TextTrack.cues`</span> property then returns a `TextTrackCueList` containing the cues for that particular track.

    let video = document.getElementById("video");
    video.onplay = function () {
      console.log(video.textTracks[0].cues);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#texttrackcuelist">HTML Living Standard<br />
<span class="small">The definition of 'TextTrackCueList' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`TextTrackCueList`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCueList</a>

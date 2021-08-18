TextTrackCue
============

`TextTrackCue` is an abstract class which is used as the basis for the various derived cue types, such as [`VTTCue`](vttcue); you will instead work with those derived types. These cues represent a string of text that is presented for some duration of time during the performance of a [`TextTrack`](texttrack). The cue includes the start time (the time at which the text will be displayed) and the end time (the time at which it will be removed from the display), as well as other information.

Properties
----------

*This interface also inherits properties from [`EventTarget`](eventtarget).*

 <span class="page-not-created">`TextTrackCue.track`</span> <span class="badge inline readonly">Read only </span>   
The [`TextTrack`](texttrack) that this cue belongs to, or `null` if it doesn't belong to any.

<span class="page-not-created">`TextTrackCue.id`</span>  
A [`DOMString`](domstring) that identifies the cue.

<span class="page-not-created">`TextTrackCue.startTime`</span>  
A `double` that represents the video time that the cue will start being displayed, in seconds.

<span class="page-not-created">`TextTrackCue.endTime`</span>  
A `double` that represents the video time that the cue will stop being displayed, in seconds.

<span class="page-not-created">`TextTrackCue.pauseOnExit`</span>  
A `boolean` for whether the video will pause when this cue stops being displayed.

Event handlers
--------------

<span class="page-not-created">`TextTrackCue.onenter`</span>  
The event handler for the `enter` event.

<span class="page-not-created">`TextTrackCue.onexit`</span>  
The event handler for the `exit` event.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#texttrackcue">HTML Living Standard<br />
<span class="small">The definition of 'TextTrackCue' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/#texttrackcue">HTML5<br />
<span class="small">The definition of 'TextTrackCue' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`TextTrackCue`

23

≤79

31

10

≤12.1

6

≤37

25

31

≤12.1

7

1.5

`endTime`

23

≤79

31

10

≤12.1

6.1

≤37

25

31

≤12.1

8

1.5

`enter_event`

23

≤79

?

?

?

?

≤37

25

?

?

?

1.5

`exit_event`

23

≤79

?

?

?

?

≤37

25

?

?

?

1.5

`id`

23

≤79

31

10

≤12.1

6.1

≤37

25

31

≤12.1

8

1.5

`onenter`

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

7

1.5

`onexit`

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

7

1.5

`pauseOnExit`

23

≤79

31

10

≤12.1

6.1

≤37

25

31

≤12.1

8

1.5

`startTime`

23

≤79

31

10

≤12.1

6.1

≤37

25

31

≤12.1

8

1.5

`track`

23

≤79

31

10

≤12.1

6.1

≤37

25

31

≤12.1

8

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrackCue</a>

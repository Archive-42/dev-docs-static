VTTCue
======

  
The `VTTCue` interface—part of the API for handling WebVTT (text tracks on media presentations)—describes and controls the text track associated with a particular [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) element.

Constructor
-----------

[`VTTCue(startTime, endTime, text)`](vttcue/vttcue)  
Returns a newly created `VTTCue` object that covers the given time range and has the given text.

### Param

 `startTime`   
The time, in seconds and fractions of a second, that describes the beginning of the range of the <a href="https://html.spec.whatwg.org/multipage/media.html#media-data" id="text-track-model:media-data">media data</a> to which the cue applies.

 `endTime`   
The time, in seconds and fractions of a second, that describes the end of the range of the <a href="https://html.spec.whatwg.org/multipage/media.html#media-data" id="text-track-model:media-data-2">media data</a> to which the cue applies.

 `text`   
The raw text of the cue, and rules for its interpretation.

Properties
----------

*This interface also inherits properties from [`TextTrackCue`](texttrackcue).*

<span class="page-not-created">`VTTCue.region`</span>  
A [`VTTRegion`](vttregion) object describing the video's sub-region that the cue will be drawn onto, or `null` if none is assigned.

<span class="page-not-created">`VTTCue.vertical`</span>  
Returns an enum representing the cue writing direction.

<span class="page-not-created">`VTTCue.snapToLines`</span>  
Returns true if the <span class="page-not-created">`VTTCue.line`</span> attribute is an integer number of lines or a percentage of the video size.

<span class="page-not-created">`VTTCue.line`</span>  
Returns the line positioning of the cue. This can be the string `auto` or a number whose interpretation depends on the value of <span class="page-not-created">`VTTCue.snapToLines`</span>.

<span class="page-not-created">`VTTCue.lineAlign`</span>  
Returns an enum representing the alignment of the <span class="page-not-created">`VTTCue.line`</span>.

<span class="page-not-created">`VTTCue.position`</span>  
Returns the indentation of the cue within the line. This can be the string `auto` or a number representing the percentage of the <span class="page-not-created">`VTTCue.region`</span>, or the video size if <span class="page-not-created">`VTTCue.region`</span> is `null`.

<span class="page-not-created">`VTTCue.positionAlign`</span>  
Returns an enum representing the alignment of the cue. This is used to determine what the <span class="page-not-created">`VTTCue.position`</span> is anchored to. The default is `auto`.

<span class="page-not-created">`VTTCue.size`</span>  
Returns a `double` representing the size of the cue, as a percentage of the video size.

<span class="page-not-created">`VTTCue.textAlign`</span>  
Returns an enum representing the alignment of all the lines of text within the cue box.

<span class="page-not-created">`VTTCue.text`</span>  
Returns a [`DOMString`](domstring) with the contents of the cue.

Methods
-------

<span class="page-not-created">`getCueAsHTML()`</span>  
Returns the cue text as a [`DocumentFragment`](documentfragment).

Example
-------

### HTML

    <video controls src="https://interactive-examples.mdn.mozilla.net/media/examples/flower.webm"></video>

### CSS

    video {
      width: 320px;
      height: 180px;
    }

### JavaScript

    let video = document.querySelector('video');
    video.addEventListener('loadedmetadata', () => {
      const track = video.addTextTrack("captions", "简体中文Subtitles", "zh_CN");
      track.mode = "showing";

      const cueCn = new VTTCue(0, 2.500, '字幕会在0至2.5秒间显示');
      track.addCue(cueCn);

      const cueEn = new VTTCue(2.6, 4, 'Subtitles will display between 2.6 and 4 seconds');
      track.addCue(cueEn);
    });

### Result

> Chrome: Please Open in JSFiddle to view the live sample. Embed live sample can not show subtitles in Chrome.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webvtt/">WebVTT: The Web Video Text Tracks Format</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`VTTCue`

23

≤79

26

No

≤12.1

6.1

≤37

25

Yes

≤12.1

8

1.5

`VTTCue`

33

≤79

Yes

No

20

6.1

4.4.3

33

Yes

20

8

2.0

`align`

23

≤79

Yes

No

≤12.1

6.1

≤37

25

Yes

≤12.1

8

1.5

`getCueAsHTML`

23

≤79

Yes

No

≤12.1

6.1

≤37

25

Yes

≤12.1

8

1.5

`line`

23

≤79

Yes

No

≤12.1

6.1

≤37

25

Yes

≤12.1

8

1.5

`lineAlign`

No

No

Yes

No

No

14.1

No

No

Yes

No

14.5

No

`position`

23

≤79

Yes

No

≤12.1

6.1

≤37

25

Yes

≤12.1

8

1.5

`positionAlign`

No

No

Yes

No

No

14.1

No

No

Yes

No

14.5

No

`region`

No

No

Yes

No

No

14.1

No

No

Yes

No

14.5

No

`size`

23

≤79

Yes

No

≤12.1

6.1

≤37

25

Yes

≤12.1

8

1.5

`snapToLines`

23

≤79

Yes

No

≤12.1

6.1

≤37

25

Yes

≤12.1

8

1.5

`text`

23

≤79

Yes

No

≤12.1

6.1

≤37

25

Yes

≤12.1

8

1.5

`vertical`

23

≤79

Yes

No

15

6.1

≤37

25

Yes

14

8

1.5

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VTTCue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VTTCue</a>

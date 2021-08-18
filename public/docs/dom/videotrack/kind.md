VideoTrack.kind
===============

The `kind` property contains a string indicating the category of video contained in the **[`VideoTrack`](../videotrack)**. The `kind` can be used to determine the scenarios in which specific tracks should be enabled or disabled. See [Video track kind strings](#video_track_kind_strings) for a list of the kinds available for video tracks.

Syntax
------

    var trackKind = VideoTrack.kind;

### Value

A [`DOMString`](../domstring) specifying the type of content the media represents. The string is one of those found in [Video track kind strings](#video_track_kind_strings) below.

Video track kind strings
------------------------

The kinds available for video tracks are:

`"alternative"`  
A potential alternative to the main track, such as a different video take or a version of the soundtrack with only the music and no dialogue.

`"captions"`  
A version of the main video track with captions burnt in.

`"main"`  
The primary video track.

`"sign"`  
A sign-language interpretation of an audio track.

`"subtitles"`  
A version of the main video track with subtitles burnt in.

`"commentary"`  
A video track containing a commentary. This might be used to contain the director's commentary track on a movie, for example.

 `""` (empty string)  
The track doesn't have an explicit kind, or the kind provided by the track's metadata isn't recognized by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-videotrack-kind">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrack: kind' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`kind`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack/kind" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack/kind</a>

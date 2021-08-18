# AudioTrack.kind

The `kind` property contains a string indicating the category of audio contained in the **[`AudioTrack`](../audiotrack)**. The `kind` can be used to determine the scenarios in which specific tracks should be enabled or disabled. See [Audio track kind strings](#audio_track_kind_strings) for a list of the kinds available for audio tracks.

## Syntax

    var trackKind = AudioTrack.kind;

### Value

A [`DOMString`](../domstring) specifying the type of content the media represents. The string is one of those found in [Audio track kind strings](#audio_track_kind_strings) below.

## Audio track kind strings

The kinds available for audio tracks are:

`"alternative"`  
A potential alternative to the main track, such as a different audio take or a version of the soundtrack with only the music and no dialogue.

`"descriptions"`  
An audio track providing audible descriptions of the action depicted in a video track.

`"main"`  
The primary audio track.

`"main-desc"`  
The primary audio track with audio descriptions mixed into it.

`"translation"`  
A translated version of the primary audio track.

`"commentary"`  
An audio track containing a commentary. This might be used to contain the director's commentary track on a movie, for example.

`""` (empty string)  
The track doesn't have an explicit kind, or the kind provided by the track's metadata isn't recognized by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#dom-audiotrack-kind">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrack: kind' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotrack-kind">HTML5<br />
<span class="small">The definition of 'AudioTrack.kind' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/kind" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/kind</a>

# AudioTrack

The `AudioTrack` interface represents a single audio track from one of the HTML media elements, [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video). The most common use for accessing an `AudioTrack` object is to toggle its [`enabled`](audiotrack/enabled) property in order to mute and unmute the track.

## Properties

[`enabled`](audiotrack/enabled)  
A Boolean value which controls whether or not the audio track's sound is enabled. Setting this value to `false` mutes the track's audio.

[`id`](audiotrack/id) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) which uniquely identifies the track within the media. This ID can be used to locate a specific track within an audio track list by calling [`AudioTrackList.getTrackById()`](audiotracklist/gettrackbyid). The ID can also be used as the fragment part of the URL if the media supports seeking by media fragment per the [Media Fragments URI specification](https://www.w3.org/TR/media-frags/).

[`kind`](audiotrack/kind) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) specifying the category into which the track falls. For example, the main audio track would have a `kind` of `"main"`.

[`label`](audiotrack/label) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) providing a human-readable label for the track. For example, an audio commentary track for a movie might have a `label` of `"Commentary with director John Q. Public and actors John Doe and Jane Eod."` This string is empty if no label is provided.

[`language`](audiotrack/language) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) specifying the audio track's primary language, or an empty string if unknown. The language is specified as a BCP 47 ([RFC 5646](https://tools.ietf.org/html/rfc5646)) language code, such as `"en-US"` or `"pt-BR"`.

[`sourceBuffer`](audiotrack/sourcebuffer) <span class="badge inline readonly">Read only </span>  
The [`SourceBuffer`](sourcebuffer) that created the track. Returns null if the track was not created by a [`SourceBuffer`](sourcebuffer) or the [`SourceBuffer`](sourcebuffer) has been removed from the [`MediaSource.sourceBuffers`](mediasource/sourcebuffers) attribute of its parent media source.

## Usage notes

To get an `AudioTrack` for a given media element, use the element's [`audioTracks`](htmlmediaelement/audiotracks) property, which returns an [`AudioTrackList`](audiotracklist) object from which you can get the individual tracks contained in the media:

    var el = document.querySelector("video");
    var tracks = el.audioTracks;

You can then access the media's individual tracks using either array syntax or functions such as [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach).

This first example gets the first audio track on the media:

    var firstTrack = tracks[0];

The next example scans through all of the media's audio tracks, enabling any that are in the user's preferred language (taken from a variable `userLanguage`) and disabling any others.

    tracks.forEach(function(track) {
      if (track.language === userLanguage) {
        track.enabled = true;
      } else {
        track.enabled = false;
      }
    });

The [`language`](audiotrack/language) is in standard ([RFC 5646](https://tools.ietf.org/html/rfc5646)) format. For US English, this would be `"en-US"`, for example.

## Example

This example returns an array of track kinds and labels for potential use in a user interface to select audio tracks for a specified media element. The list is filtered to only allow certain track kinds through.

    function getTrackList(el) {
      var trackList = [];
      const wantedKinds = [
        "main", "alternative", "main-desc", "translation", "commentary"
      ];

      el.audioTracks.forEach(function(track) {
        if (wantedKinds.includes(track.kind)) {
          trackList.push({
            id: track.id,
            kind: track.kind,
            label: track.label
          });
        }
      });
      return trackList;
    }

The resulting `trackList` contains an array of audio tracks whose `kind` is one of those in the array `wantedKinds`, with each entry providing the track's [`id`](audiotrack/id), [`kind`](audiotrack/kind), and [`label`](audiotrack/label).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#audiotrack">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#audiotrack">HTML5<br />
<span class="small">The definition of 'AudioTrack' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`AudioTrack`

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

`enabled`

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

`id`

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

`label`

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

`sourceBuffer`

51

79

12-79

No

11

38

6.1

No

51

No

41

7

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack</a>

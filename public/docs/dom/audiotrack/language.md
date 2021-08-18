# AudioTrack.language

The read-only **[`AudioTrack`](../audiotrack)** property `language` returns a string identifying the language used in the audio track. For tracks that include multiple languages (such as a movie in English in which a few lines are spoken in other languages), this should be the video's primary language.

## Syntax

    var audioTrackLanguage = AudioTrack.language;

### Value

A [`DOMString`](../domstring) specifying the BCP 47 ([RFC 5646](https://tools.ietf.org/html/rfc5646)) format language tag of the primary language used in the audio track, or an empty string (`""`) if the language is not specified or known, or if the track doesn't contain speech.

For example, if the primary language used in the track is United States English, this value would be `"en-US"`. For Brazilian Portuguese, the value would be `"pt-BR"`.

## Example

This example locates all of a media element's primary language and translated audio tracks and returns a list of objects containing each of those tracks' [`id`](id), [`kind`](kind), and `language`.

This could then be used to build a user interface for selecting the language the user would like to listen to while watching a movie, for example.

    function getAvailableLanguages(el) {
      var trackList = [];
      const wantedKinds = [
        "main", "translation"
      ];

      el.audioTracks.forEach(function(track) {
        if (wantedKinds.includes(track.kind)) {
          trackList.push({
            id: track.id,
            kind: track.kind,
            language: track.language
          });
        }
      });
      return trackList;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#dom-audiotrack-language">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrack.language' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotrack-language">HTML5<br />
<span class="small">The definition of 'AudioTrack.language' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/language" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/language</a>

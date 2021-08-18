# AudioTrack.label

The read-only **[`AudioTrack`](../audiotrack)** property `label` returns a string specifying the audio track's human-readable label, if one is available; otherwise, it returns an empty string.

## Syntax

    var audioTrackLabel = AudioTrack.label;

### Value

A [`DOMString`](../domstring) specifying the track's human-readable label, if one is available in the track metadata. Otherwise, an empty string (`""`) is returned.

For example, a track whose [`kind`](kind) is `"commentary"` might have a `label` such as `"Commentary with director Mark Markmarkimark and star Donna Donnalidon"`.

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

The resulting `trackList` contains an array of audio tracks whose `kind` is one of those in the array `wantedKinds`, with each entry providing the track's [`id`](id), [`kind`](kind), and [`label`](label).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#dom-audiotrack-label">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrack.label' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotrack-label">HTML5<br />
<span class="small">The definition of 'AudioTrack.label' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/label" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/label</a>

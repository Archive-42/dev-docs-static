# AudioTrack.enabled

The **[`AudioTrack`](../audiotrack)** property `enabled` specifies whether or not the described audio track is currently enabled for use. If the track is disabled by setting `enabled` to `false`, the track is muted and does not produce audio.

## Syntax

    isAudioEnabled = AudioTrack.enabled;

    AudioTrack.enabled = true | false;

### Value

The `enabled` property is a Boolean whose value is `true` if the track is enabled; enabled tracks produce audio while the media is playing. Setting `enabled` to `false` effectively mutes the audio track, preventing it from contributing to the media's audio performance.

## Example

This example switches between the main and commentary audio tracks of a media element.

    function swapCommentaryMain() {
      var videoElem = document.getElementById("main-video");
      var audioTrackMain;
      var audioTrackCommentary;

      videoElem.audioTracks.forEach(track) {
        if (track.kind === "main") {
          audioTrackMain = track;
        } else if (track.kind === "commentary") {
          audioTrackCommentary = track;
        }
      }

      if (audioTrackMain && audioTrackCommentary) {
        var commentaryEnabled = audioTrackCommentary.enabled;
        audioTrackCommentary.enabled = audioTrackMain.enabled;
        audioTrackMain.enabled = commentaryEnabled;
      }
    }

The `swapCommentaryMain()` function above finds within the audio tracks of the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element `"main-video"` the audio tracks whose [`kind`](kind) values are `"main"` and `"commentary"`. These represent the primary audio track and the commentary track.

**Note:** This example assumes that there is only one of each kind of track in the video, but this is not necessarily the case.

The element's audio tracks are then scanned through using the JavaScript [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) method (although the [`audioTracks`](../htmlmediaelement/audiotracks) property of a media element isn't actually a JavaScript array, it can be accessed like one for the most part).

The scan looks for the tracks whose [`kind`](kind) values are `"main"` and `"commentary"` and remembers those [`AudioTrack`](../audiotrack) objects. Once those have been found, the values of the two tracks' `enabled` properties are exchanged, which results in swapping which of the two tracks is currently active.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#dom-audiotrack-enabled">HTML Living Standard<br />
<span class="small">The definition of 'AudioTrack.enabled' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-audiotrack-enabled">HTML5<br />
<span class="small">The definition of 'AudioTrack.enabled' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/enabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioTrack/enabled</a>

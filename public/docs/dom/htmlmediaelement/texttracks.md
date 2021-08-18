# HTMLMediaElement.textTracks

**Draft**

This page is not complete.

The read-only `textTracks` property on [`HTMLMediaElement`](../htmlmediaelement) objects returns a [`TextTrackList`](../texttracklist) object listing all of the [`TextTrack`](../texttrack) objects representing the media element's text tracks, in the same order as in the list of text tracks.

You can detect when tracks are added to and removed from an `<audio>` or `<video>` element using the `addtrack` and `removetrack` events. However, these events aren't sent directly to the media element itself. Instead, they're sent to the track list object of the [`HTMLMediaElement`](../htmlmediaelement) that corresponds to the type of track that was added to the element

The returned list is _live_; that is, as tracks are added to and removed from the media element, the list's contents change dynamically. Once you have a reference to the list, you can monitor it for changes to detect when new text tracks are added or existing ones removed.

## Syntax

    var textTracks = mediaElement.textTracks;

### Value

A [`TextTrackList`](../texttracklist) object representing the list of text tracks included in the media element. The list of tracks can be accessed using array notation, or using the object's `getTrackById()` method.

Each track is represented by a [`TextTrack`](../texttrack) object which provides information about the track.

## Examples

We start with a `<video>` that has several `<track>` children

    <video controls poster="/images/sample.gif">
      <source src="sample.mp4" type="video/mp4">
      <source src="sample.ogv" type="video/ogv">
      <track kind="captions" src="sampleCaptions.vtt" srclang="en">
      <track kind="descriptions" src="sampleDescriptions.vtt" srclang="en">
      <track kind="chapters" src="sampleChapters.vtt" srclang="en">
      <track kind="subtitles" src="sampleSubtitles_de.vtt" srclang="de">
      <track kind="subtitles" src="sampleSubtitles_en.vtt" srclang="en">
      <track kind="subtitles" src="sampleSubtitles_ja.vtt" srclang="ja">
      <track kind="subtitles" src="sampleSubtitles_oz.vtt" srclang="oz">
      <track kind="metadata" src="keyStage1.vtt" srclang="en" label="Key Stage 1">
      <track kind="metadata" src="keyStage2.vtt" srclang="en" label="Key Stage 2">
      <track kind="metadata" src="keyStage3.vtt" srclang="en" label="Key Stage 3">
    </video>

The `HTMLMediaElement.textTracks` returns a `textTracksList` thru which we can iterate. Here we print all the properties of each English track to the console.

    var tracks = document.querySelector('video').textTracks;

    for (var i = 0, L = tracks.length; i < L; i++) { /* tracks.length == 10 */
       if (tracks[i].language == 'en') {
          console.dir(tracks[i]);
       }
    }

## Properties & Methods

### properties

length  
Returns the number of text tracks in `TextTrackList` object.

### methods

getTrackById()  
The `getTrackById(id)` method returns the first `TextTrack` in the `TextTrackList` object that matches the id, or null if there is no match.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-media-texttracks">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.textTracks' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.textTracks' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`textTracks`

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

1.0

## See also

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
- [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) and [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
- [`VideoTrack`](../videotrack) and [`VideoTrackList`](../videotracklist)
- [`AudioTrack`](../audiotrack) and [`AudioTrackList`](../audiotracklist)
- VideoTrackList `change`, `addtrack` and `removetrack` events
- Audio TrackList `change`, `addtrack` and `removetrack` events

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/textTracks" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/textTracks</a>

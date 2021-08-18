&lt;track&gt;: The Embed Text Track element
===========================================

The `<track>` is used as a child of the media elements, [`<audio>`](audio) and [`<video>`](video). It lets you specify timed text tracks (or time-based data), for example to automatically handle subtitles. The tracks are formatted in [WebVTT format](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) (`.vtt` files) — Web Video Text Tracks.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>As it is a void element, the start tag must be present and the end tag must not be present.</td></tr><tr class="even"><td>Permitted parents</td><td><p>A media element, <a href="audio"><code>&lt;audio&gt;</code></a> or <a href="video"><code>&lt;video&gt;</code></a>.</p></td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement"><code>HTMLTrackElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`default`  
This attribute indicates that the track should be enabled unless the user's preferences indicate that another track is more appropriate. This may only be used on one `track` element per media element.

`kind`  
How the text track is meant to be used. If omitted the default kind is `subtitles`. If the attribute contains an invalid value, it will use `metadata` (Versions of Chrome earlier than 52 treated an invalid value as `subtitles`). The following keywords are allowed:

-   `subtitles`
    -   Subtitles provide translation of content that cannot be understood by the viewer. For example speech or text that is not English in an English language film.
    -   Subtitles may contain additional content, usually extra background information. For example the text at the beginning of the Star Wars films, or the date, time, and location of a scene.
-   `captions`
    -   Closed captions provide a transcription and possibly a translation of audio.
    -   It may include important non-verbal information such as music cues or sound effects. It may indicate the cue's source (e.g. music, text, character).
    -   Suitable for users who are deaf or when the sound is muted.
-   `descriptions`
    -   Textual description of the video content.
    -   Suitable for users who are blind or where the video cannot be seen.
-   `chapters`
    -   Chapter titles are intended to be used when the user is navigating the media resource.
-   `metadata`
    -   Tracks used by scripts. Not visible to the user.

`label`  
A user-readable title of the text track which is used by the browser when listing available text tracks.

`src`  
Address of the track (`.vtt` file). Must be a valid URL. This attribute must be specified and its URL value must have the same origin as the document — unless the [`<audio>`](audio) or [`<video>`](video) parent element of the `track` element has a `crossorigin` attribute.

`srclang`  
Language of the track text data. It must be a valid [BCP 47](https://r12a.github.io/app-subtags/) language tag. If the `kind` attribute is set to `subtitles`, then `srclang` must be defined.

Usage notes
-----------

### Track data types

The type of data that `track` adds to the media is set in the `kind` attribute, which can take values of `subtitles`, `captions`, `descriptions`, `chapters` or `metadata`. The element points to a source file containing timed text that the browser exposes when the user requests additional data.

A `media` element cannot have more than one `track` with the same `kind`, `srclang`, and `label`.

### Detecting cue changes

The underlying [`TextTrack`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrack), indicated by the <span class="page-not-created">`track`</span> property, receives a [`cuechange`](https://developer.mozilla.org/en-US/docs/Web/API/TextTrack/cuechange_event) event every time the currently-presented cue is changed. This happens even if the track isn't associated with a media element.

If the track *is* associated with a media element, using the [`<track>`](track) element as a child of the [`<audio>`](audio) or [`<video>`](video) element, the `cuechange` event is also sent to the [`HTMLTrackElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement).

    let textTrackElem = document.getElementById("texttrack");

    textTrackElem.addEventListener("cuechange", (event) => {
      let cues = event.target.track.activeCues;
    });

In addition, you can use the `oncuechange` event handler:

    let textTrackElem = document.getElementById("texttrack");

    textTrackElem.oncuechange = (event) => {
      let cues = event.target.track.activeCues;
    });

Examples
--------

    <video controls poster="/images/sample.gif">
       <source src="sample.mp4" type="video/mp4">
       <source src="sample.ogv" type="video/ogv">
       <track kind="captions" src="sampleCaptions.vtt" srclang="en">
       <track kind="descriptions"
         src="sampleDescriptions.vtt" srclang="en">
       <track kind="chapters" src="sampleChapters.vtt" srclang="en">
       <track kind="subtitles" src="sampleSubtitles_de.vtt" srclang="de">
       <track kind="subtitles" src="sampleSubtitles_en.vtt" srclang="en">
       <track kind="subtitles" src="sampleSubtitles_ja.vtt" srclang="ja">
       <track kind="subtitles" src="sampleSubtitles_oz.vtt" srclang="oz">
       <track kind="metadata" src="keyStage1.vtt" srclang="en"
         label="Key Stage 1">
       <track kind="metadata" src="keyStage2.vtt" srclang="en"
         label="Key Stage 2">
       <track kind="metadata" src="keyStage3.vtt" srclang="en"
         label="Key Stage 3">
       <!-- Fallback -->
       ...
    </video>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#the-track-element">HTML Living Standard<br />
<span class="small">The definition of 'track element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#the-track-element">HTML5<br />
<span class="small">The definition of 'track element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`track`

23

12

31

10

12.1

6

Yes

Doesn't work for fullscreen video.

25

Doesn't work for fullscreen video.

31

?

6

1.5

Doesn't work for fullscreen video.

`default`

23

12

31

10

12.1

6

4.4

25

31

?

?

1.5

`kind`

23

12

31

10

12.1

6

4.4

25

31

?

?

1.5

`label`

23

12

31

10

12.1

6

4.4

25

31

?

?

1.5

`src`

23

12

31

10

12.1

6

4.4

25

31

?

?

1.5

`srclang`

23

12

31

10

12.1

6

4.4

25

31

?

?

1.5

See also
--------

-   [WebVTT text track format](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
-   [`HTMLMediaElement.textTracks`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/textTracks)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track</a>

TextTrack.mode
==============

The [`TextTrack`](../texttrack) interface's `mode` property is a string specifying and controlling the text track's mode: `disabled`, `hidden`, or `showing`. You can read this value to determine the current mode, and you can change this value to switch modes.

Safari additionally requires the `default` boolean attribute to be set to true when implementing your own video player controls in order for the subtitles cues to be shown.

Syntax
------

    var mode = textTrack.mode;

    textTrack.mode = "disabled" | "hidden" | "showing";

### Value

A [`DOMString`](../domstring) which indicates the track's current mode. The text track mode is one of the values listed below, under [Text track mode constants](#text_track_mode_constants).

#### Text track mode constants

The text track mode—sometimes identified using the IDL enum `TextTrackMode`—must be one of the following values:

`disabled`  
The text track is currently disabled. While the track's presence is exposed in the DOM, the user agent is otherwise ignoring it. No cues are active, no events are being fired, and the user agent won't attempt to obtain the track's cues. This is the default value, unless the text track has the [`default`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-default) Boolean attribute is specified, in which case the default is `showing`.

`hidden`  
The text track is currently active but the cues aren't being displayed. If the user agent hasn't tried to obtain the track's cues yet, it will do so soon (thereby populating the track's <span class="page-not-created">`TextTrack.cues`</span> property). The user agent is keeping a list of the active cues (in the track's <span class="page-not-created">`activeCues`</span> property) and events are being fired at the corresponding times, even though the text isn't being displayed.

`showing`  
The text track is currently enabled and is visible. If the track's cues list hasn't been obtained yet, it will be soon. The <span class="page-not-created">`activeCues`</span> list is being maintained and events are firing at the appropriate times; the track's text is also being drawn appropriately based on the styling and the track's <span class="page-not-created">`kind`</span>. This is the default value if the text track's [`default`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-default) Boolean attribute is specified.

Usage notes
-----------

The default `mode` is `disabled`, unless the [`default`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-default) Boolean attribute is specified, in which case the default `mode` is `showing`. When a text track is loaded in the `disabled` state, the corresponding WebVTT file is not loaded until the state changes to either `showing` or `hidden`. This way, the resource fetch and memory usage are avoided unless the cues are actually needed.

However, that means that if you wish to perform any actions involving the track's cues while handling, for example, the `load` event—in order to process some aspect of the cues upon page load—and the track mode was initially `disabled`, you'll have to change the `mode` to either `hidden` or `showing` in order to trigger loading of the cues.

When the mode is `showing`, text tracks are performed. The exact appearance and manner of that performance varies depending on each text track's <span class="page-not-created">`kind`</span>. In general:

-   Tracks whose `kind` is `"subtitles"` or `"captions"` are rendered with the cues overlaid over the top of the video.
-   Tracks whose `kind` is `"descriptions"` are presented in a non-visual form (for example, the text might be spoken to describe the action in the video).
-   Tracks whose `kind` is `"chapters"` are used by the user agent or the Web site or Web app to construct and present an interface for navigating the named chapters, where each cue in the list represents a chapter in the media. The user can then navigate to the desired chapter, which begins at the cue's start position and ends at the cue's end position.

Example
-------

In this example, we configure the text track's cues so that every time a cue is finished, the video automatically pauses playback. This is done by setting the <span class="page-not-created">`pauseOnExit`</span> property on each cue to `true`. However, to ensure that the track's cues are available, we first set `mode` to `showing`.

    window.addEventListener("load", event => {
      let trackElem = document.querySelector("track");
      let track = trackElem.track;

      track.mode = "showing";

      for (let index=0; index < track.cues.length; index++) {
        let cue = track.cues[index];
        cue.pauseOnExit = true;
      };
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-texttrack-mode">HTML Living Standard<br />
<span class="small">The definition of 'mode' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`mode`

23

12

31

Before Firefox 52, using JavaScript to change the mode of a text track that's part of a media element would send one change event to the element's textTracks TextTrackList for each change, even if mutliple changes are made in a single pass through the Firefox event loop. Starting in Firefox 52, these changes are reflected by a single event.

10

≤12.1

6

4.4

25

31

≤12.1

7

1.5

See also
--------

-   [WebVTT](../webvtt_api)
-   [`TextTrack`](../texttrack)
-   [`TextTrackList`](../texttracklist)
-   [`TextTrackCueList`](../texttrackcuelist)
-   [`VTTCue`](../vttcue)
-   [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track)
-   [`HTMLTrackElement`](../htmltrackelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextTrack/mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextTrack/mode</a>

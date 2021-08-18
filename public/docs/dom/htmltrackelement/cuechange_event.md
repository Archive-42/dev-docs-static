HTMLTrackElement: cuechange event
=================================

The `cuechange` event fires when a [`TextTrack`](../texttrack) has changed the currently displaying cues. The event is fired at both the `TextTrack` *and* at the [`HTMLTrackElement`](../htmltrackelement) in which it's being presented, if any.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/oncuechange"><code>GlobalEventHandlers.oncuechange</code></a></td></tr></tbody></table>

Examples
--------

### On the TextTrack

You can set up a listener for the `cuechange` event on a `TextTrack` using the [`addEventListener()`](../eventtarget/addeventlistener) method:

    track.addEventListener('cuechange', function () {
      let cues = track.activeCues;  // array of current cues
    });

Or you can just set the [`oncuechange`](../globaleventhandlers/oncuechange) event handler property:

    track.oncuechange = function () {
      let cues = track.activeCues; // array of current cues
    }

### On the track element

The underlying [`TextTrack`](../texttrack), indicated by the <span class="page-not-created">`track`</span> property, receives a [`cuechange`](../texttrack/cuechange_event) event every time the currently-presented cue is changed. This happens even if the track isn't associated with a media element.

If the track *is* associated with a media element, using the [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) element as a child of the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, the `cuechange` event is also sent to the [`HTMLTrackElement`](../htmltrackelement).

    let textTrackElem = document.getElementById("texttrack");

    textTrackElem.addEventListener("cuechange", (event) => {
      let cues = event.target.track.activeCues;
    });

In addition, you can use the `oncuechange` event handler:

    let textTrackElem = document.getElementById("texttrack");

    textTrackElem.oncuechange = (event) => {
      let cues = event.target.track.activeCues;
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#event-media-cuechange">HTML Living Standard<br />
<span class="small">The definition of 'cuechange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`cuechange_event`

Yes

12

31

?

?

Yes

Yes

Yes

31

No

?

Yes

See also
--------

-   [WebVTT](https://developer.mozilla.org/en-US/docs/Glossary/WebVTT)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement/cuechange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement/cuechange_event</a>

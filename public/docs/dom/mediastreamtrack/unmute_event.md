MediaStreamTrack: unmute event
==============================

The `unmute` event is sent to a [`MediaStreamTrack`](../mediastreamtrack) when the track's source is once again able to provide media data after a period of not being able to do so. This ends the [`muted`](muted) state that began with the [`mute`](mute_event) event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onunmute"><code>onunmute</code></a></td></tr></tbody></table>

**Note:** The condition that most people think of as "muted" (that is, a user-controllable way to silence a track) is actually managed using the [`MediaStreamTrack.enabled`](enabled) property, for which there are no events.

Examples
--------

In this example, event handlers are established for the [`mute`](mute_event) and `unmute` events in order to detect when the media is not flowing from the source for the [`MediaStreamTrack`](../mediastreamtrack) stored in the variable `musicTrack`.

    musicTrack.addEventListener("mute", event => {
      document.getElementById("timeline-widget").style.backgroundColor = "#aaa";
    }, false);

    musicTrack.addEventListener("unmute", event => {
     document.getElementById("timeline-widget").style.backgroundColor = "#fff";
    }, false);

With these event handlers in place, when the track `musicTrack` enters its [`muted`](muted) state, the element with the ID `timeline-widget` gets its background color changed to `#aaa`. When the track exits the muted state—detected by the arrival of an `unmuted` event—the background color is restored to white.

You can also use the [`onunmute`](onunmute) event handler property to set up a handler for this event; similarly, the [`onmute`](onmute) event handler is available for setting up a handler for the `mute` event. The following example shows this:

    musicTrack.onmute = event => {
      document.getElementById("timeline-widget").style.backgroundColor = "#aaa";
    }

    musicTrack.mute = event = > {
      document.getElementById("timeline-widget").style.backgroundColor = "#fff";
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#event-mediastreamtrack-unmute">Media Capture and Streams<br />
<span class="small">The definition of 'unmute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`unmute_event`

Yes

12

59

No

Yes

Yes

Yes

Yes

59

Yes

Yes

Yes

See also
--------

-   [`onunmute`](onunmute) event handler property
-   [`mute`](mute_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/unmute_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/unmute_event</a>

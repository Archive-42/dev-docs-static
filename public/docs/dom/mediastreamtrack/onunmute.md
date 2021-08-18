MediaStreamTrack.onunmute
=========================

[`MediaStreamTrack`](../mediastreamtrack)'s `onunmute` event handler is called when the `unmute` event is received. Such an event is sent when the track is again able to send data.

When the `onunmute` event handler is called, the track's [`muted`](muted) flag is `false`.

Syntax
------

    track.onunmute = unmuteHandler;

### Value

`unmuteHandler` is a function which is called when the `MediaStreamTrack` receives the `unmute` event. The event handler receives as input a single parameter: an [`Event`](../event) whose <span class="page-not-created">`kind`</span> is `"unmute"`.

Example
-------

This example creates an `unmute` event handler which changes the state of a visual indicator to display the Emoji character representing a "speaker" icon.

    myTrack.onunmute = function(evt) {
      playStateIcon.innerHTML = "&#x1F508;";
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-onunmute">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrack.onunmute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onunmute`

Yes

12

59

No

Yes

11

Yes

Yes

59

Yes

11

Yes

See also
--------

-   The `unmute` event and its type, [`Event`](../event).
-   [`MediaStreamTrack.muted`](muted) to determine if a track is currently muted
-   [`MediaStreamTrack.onmute`](onmute), the event handler for the [`MediaStreamTrack.mute_event`](mute_event) event.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onunmute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onunmute</a>

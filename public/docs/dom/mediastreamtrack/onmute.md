MediaStreamTrack.onmute
=======================

[`MediaStreamTrack`](../mediastreamtrack)'s `onmute` event handler is called when the `mute` event is received. Such an event is sent when the track is temporarily not able to send data.

Syntax
------

    track.onmute = muteHandler;

### Value

A function to serve as an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for the `mute` event. The event handler function receives a single parameter: the event object, which is a simple [`Event`](../event) object.

Example
-------

In this example, an `onmute` handler is established to set the content HTML of an element to display the "muted speaker" Emoji.

    myTrack.onmute = function(evt) {
      playStateIcon.innerHTML = "&#1F507;";
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-onmute">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrack.onmute' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onmute`

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

-   The `mute` event and its type, [`Event`](../event).
-   [`MediaStreamTrack.muted`](muted) to determine if a track is currently muted
-   [`MediaStreamTrack.onunmute`](onunmute), the event handler for the <span class="page-not-created">`unmute`</span> event.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onmute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onmute</a>

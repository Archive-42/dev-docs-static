MediaStreamTrack.onended
========================

The `MediaStreamTrack.onended` event handler is used to specify a function which serves as an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) to be called when the `ended` event occurs on the track. This event occurs when the track will no longer provide data to the stream for any reason, including the end of the media input being reached, the user revoking needed permissions, the source device being removed, or the remote peer ending a connection.

Syntax
------

    MediaStreamTrack.onended = function;

### Value

A function to serve as an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for the `ended` event. The event handler function receives a single parameter: the event object, which is a simple [`Event`](../event) object.

Examples
--------

This example sets up an event handler for the `ended` event which changes an on-screen icon to indicate that the track is no longer active.

    track.onended = function(event) {
      let statusElem = document.getElementById("status-icon");

      statusElem.src = "/images/stopped-icon.png";
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-onended">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrack.onended' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onended`

Yes

12

50

No

Yes

11

Yes

Yes

50

Yes

11

Yes

See also
--------

-   The `ended` event and its type, [`Event`](../event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onended" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/onended</a>

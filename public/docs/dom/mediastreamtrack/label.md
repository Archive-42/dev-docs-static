MediaStreamTrack.label
======================

The `MediaStreamTrack.label` read-only property returns a [`DOMString`](../domstring) containing a [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)-assigned label that identifies the track source, as in `"internal microphone"`. The string may be left empty and is empty as long as no source has been connected. When the track is deassociated from its source, the label is not changed.

Syntax
------

    const label = track.label

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-label">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamTrack.label' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`label`

Yes

12

Yes

No

Yes

11

Yes

Yes

Yes

Yes

11

Yes

See also
--------

-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/label" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/label</a>

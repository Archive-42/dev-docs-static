MediaStreamConstraints
======================

The `MediaStreamConstraints` dictionary is used when calling [`getUserMedia()`](mediadevices/getusermedia) to specify what kinds of tracks should be included in the returned [`MediaStream`](mediastream), and, optionally, to establish constraints for those tracks' settings.

To learn more about how constraints work, see [Capabilities, constraints, and settings](media_streams_api/constraints).

Properties
----------

Some combination—but not necessarily all—of the following properties will exist on the object.

### Track constraints

[`audio`](mediastreamconstraints/audio)  
Either a Boolean (which indicates whether or not an audio track is requested) or a [`MediaTrackConstraints`](mediatrackconstraints) object providing the constraints which must be met by the audio track included in the returned [`MediaStream`](mediastream). If constraints are specified, an audio track is inherently requested.

[`video`](mediastreamconstraints/video)  
Either a Boolean (which indicates whether or not a video track is requested) or a [`MediaTrackConstraints`](mediatrackconstraints) object providing the constraints which must be met by the video track included in the returned [`MediaStream`](mediastream). If constraints are specified, a video track is inherently requested.

### Security

<span class="page-not-created">`peerIdentity`</span>  
A [`DOMString`](domstring) identifying the peer who has sole access to the stream. If this property is specified, only the indicated peer can receive and use the stream. Streams isolated in this way can only be displayed in a media element ([`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)) where the content is protected just as if [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) cross-origin rules were in effect. When a peer identity is set, [`MediaStreamTrack`](mediastreamtrack)s from that peer have their <span class="page-not-created">`isolated`</span> flag set to `true`.

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

`MediaStreamConstraints`

53

≤79

38

No

Yes

?

53

53

38

Yes

?

6.0

`audio`

Yes

≤79

38

No

Yes

?

Yes

Yes

38

Yes

?

Yes

`video`

Yes

≤79

38

No

Yes

?

Yes

Yes

38

Yes

?

Yes

See also
--------

-   [`MediaDevices.getUserMedia()`](mediadevices/getusermedia)
-   [`MediaStreamTrack.getConstraints()`](mediastreamtrack/getconstraints)
-   [`MediaStreamTrack.applyConstraints()`](mediastreamtrack/applyconstraints)
-   [`MediaDevices.getSupportedConstraints()`](mediadevices/getsupportedconstraints)
-   [`MediaTrackSupportedConstraints`](mediatracksupportedconstraints)
-   [`MediaStreamTrack.getSettings()`](mediastreamtrack/getsettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints</a>

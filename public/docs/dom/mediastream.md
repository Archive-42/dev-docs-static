# MediaStream

The `MediaStream` interface represents a stream of media content. A stream consists of several **tracks** such as video or audio tracks. Each track is specified as an instance of [`MediaStreamTrack`](mediastreamtrack).You can obtain a MediaStream object either by using the constructor or by calling [`MediaDevices.getUserMedia()`](mediadevices/getusermedia).

Some user agents subclass this interface to provide more precise information or functionality, like in [`CanvasCaptureMediaStreamTrack`](canvascapturemediastreamtrack).

## Constructor

[`MediaStream()`](mediastream/mediastream)  
Creates and returns a new MediaStream object. You can create an empty stream, a stream which is based upon an existing stream, or a stream that contains a specified list of tracks (specified as an array of [`MediaStreamTrack`](mediastreamtrack) objects).

## Properties

_This interface inherits properties from its parent, [`EventTarget`](eventtarget)._

[`MediaStream.active`](mediastream/active) <span class="badge inline readonly">Read only </span>  
A Boolean value that returns `true` if the `MediaStream` is active, or `false` otherwise.

[`MediaStream.ended`](mediastream/ended) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
A Boolean value set to `true` if the end of the stream has been reached. This has been removed from the specification; you should instead check the value of [`MediaStreamTrack.readyState`](mediastreamtrack/readystate) to see if its value is `ended` for the track or tracks you want to ensure have finished playing.

<!-- -->

[`MediaStream.id`](mediastream/id) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) containing 36 characters denoting a universally unique identifier (UUID) for the object.

### Event handlers

[`MediaStream.onaddtrack`](mediastream/onaddtrack)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) containing the action to perform when an `addtrack` event is fired when a new [`MediaStreamTrack`](mediastreamtrack) object is added.

[`MediaStream.onremovetrack`](mediastream/onremovetrack)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) containing the action to perform when a `removetrack` event is fired when a [`MediaStreamTrack`](mediastreamtrack) object is removed from it.

## Methods

_This interface inherits methods from its parent, [`EventTarget`](eventtarget)._

[`MediaStream.addTrack()`](mediastream/addtrack)  
Stores a copy of the [`MediaStreamTrack`](mediastreamtrack) given as argument. If the track has already been added to the `MediaStream` object, nothing happens.

<!-- -->

[`MediaStream.clone()`](mediastream/clone)  
Returns a clone of the `MediaStream` object. The clone will, however, have a unique value for [`id`](mediastream/id).

<!-- -->

[`MediaStream.getAudioTracks()`](mediastream/getaudiotracks)  
Returns a list of the [`MediaStreamTrack`](mediastreamtrack) objects stored in the `MediaStream` object that have their `kind` attribute set to `audio`. The order is not defined, and may not only vary from one browser to another, but also from one call to another.

<!-- -->

[`MediaStream.getTrackById()`](mediastream/gettrackbyid)  
Returns the track whose ID corresponds to the one given in parameters, `trackid`. If no parameter is given, or if no track with that ID does exist, it returns `null`. If several tracks have the same ID, it returns the first one.

[`MediaStream.getTracks()`](mediastream/gettracks)  
Returns a list of all [`MediaStreamTrack`](mediastreamtrack) objects stored in the `MediaStream` object, regardless of the value of the `kind` attribute. The order is not defined, and may not only vary from one browser to another, but also from one call to another.

<!-- -->

[`MediaStream.getVideoTracks()`](mediastream/getvideotracks)  
Returns a list of the [`MediaStreamTrack`](mediastreamtrack) objects stored in the `MediaStream` object that have their `kind` attribute set to `"video"`. The order is not defined, and may not only vary from one browser to another, but also from one call to another.

<!-- -->

<span class="page-not-created">`MediaStream.removeTrack()`</span>  
Removes the [`MediaStreamTrack`](mediastreamtrack) given as argument. If the track is not part of the `MediaStream` object, nothing happens.

## Events

[`addtrack`](mediastream/addtrack_event)  
Fired when a new [`MediaStreamTrack`](mediastreamtrack) object is added.  
Also available via the [`onaddtrack`](mediastream/onaddtrack) property.

[`removetrack`](mediastream/removetrack_event)  
Fired when a [`MediaStreamTrack`](mediastreamtrack) object has been removed.  
Also available via the [`onremovetrack`](mediastream/onremovetrack) property.

<!-- -->

<span class="page-not-created">`active`</span>  
Fired when the MediaStream is activated.

<!-- -->

<span class="page-not-created">`inactive`</span>  
Fired when the MediaStream is inactivated.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastream">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStream' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`MediaStream`

55

21

12

15

No

42

15

11

55

≤37

55

25

15

42

14

11

6.0

1.5

`MediaStream`

21

12

44

No

42

11

37

25

42

No

11

6.0

`active`

45

12

52

No

No

11

45

45

52

No

11

5.0

`active_event`

45

≤79

?

No

?

?

45

45

?

No

?

5.0

`addTrack`

26

12

44

No

No

11

37

26

No

No

11

1.5

`addtrack_event`

Yes

12

50

No

No

Yes

Yes

Yes

50

No

Yes

Yes

`clone`

45

12

48

No

No

11

45

45

48

No

11

5.0

`ended`

Yes-54

Deprecated in Chrome 52.

No

No

No

Yes-39

No

Yes-54

Deprecated in Chrome 52.

Yes-54

Deprecated in Chrome 52.

No

Yes-41

No

Yes-6.0

Deprecated in Samsung Internet 6.0.

`getAudioTracks`

26

12

22

Prior to Firefox 64, this method returned an array of `AudioStreamTrack` objects. However, `MediaStreamTrack` has now subsumed that interface's functionality.

No

Yes

11

37

26

22

Prior to Firefox 64, this method returned an array of `AudioStreamTrack` objects. However, `MediaStreamTrack` has now subsumed that interface's functionality.

No

11

1.5

`getTrackById`

26

12

49

No

No

11

37

26

49

No

11

1.5

`getTracks`

45

12

Yes

No

Yes

11

45

45

Yes

No

11

5.0

`getVideoTracks`

26

12

22

Prior to Firefox 64, this method returned an array of `VideoStreamTrack` objects. However, `MediaStreamTrack` has now subsumed that interface's functionality.

No

Yes

11

37

26

22

Prior to Firefox 64, this method returned an array of `VideoStreamTrack` objects. However, `MediaStreamTrack` has now subsumed that interface's functionality.

No

11

1.5

`id`

Yes-54

12-79

41

No

Yes-39

11

Yes-54

Yes-54

41

Yes-41

11

Yes-6.0

`inactive_event`

45

≤79

?

No

?

?

45

45

?

No

?

5.0

`label`

Yes-54

Deprecated in Chrome 45.

No

?

No

No

No

Yes-54

Deprecated in Chrome 45.

Yes-54

Deprecated in Chrome 45.

?

No

No

Yes-6.0

Deprecated in Samsung Internet 5.0.

`onactive`

45

12

?

No

?

No

45

45

?

No

No

5.0

`onaddtrack`

26

12

50

No

No

11

37

26

50

No

11

1.5

`oninactive`

45

12

?

No

?

No

45

45

?

No

No

5.0

`onremovetrack`

26

12

No

No

No

11

37

26

No

No

11

1.5

`removeTrack`

26

12

Yes

No

Yes

11

37

26

Yes

No

11

1.5

`removetrack_event`

Yes

12

No

No

No

Yes

Yes

Yes

No

No

Yes

Yes

`stop`

Yes-47

13-79

?

No

No

No

Yes-47

Yes-47

?

No

No

Yes-5.0

## See also

- Using the MediaStream API
- [WebRTC API](webrtc_api)
- [Web Audio API](web_audio_api)
- [`MediaStreamTrack`](mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream</a>

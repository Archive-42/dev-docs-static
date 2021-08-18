# MediaStreamConstraints.audio

The [`MediaStreamConstraints`](../mediastreamconstraints) dictionary's `audio` property is used to indicate what kind of audio track, if any, should be included in the [`MediaStream`](../mediastream) returned by a call to [`getUserMedia()`](../mediadevices/getusermedia).

To learn more about how constraints work, see [Capabilities, constraints, and settings](../media_streams_api/constraints).

## Syntax

    var audioConstraints = true | false | MediaTrackConstraints;

### Value

The value of the `audio` property can be specified as either of two types:

[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)  
If a Boolean value is specified, it indicates whether or not an audio track should be included in the returned stream; if it's `true`, an audio track is included; if no audio source is available or if permission is not given to use the audio source, the call to `getUserMedia()` will fail. If `false`, no audio track is included.

[`MediaTrackConstraints`](../mediatrackconstraints)  
A constraints dictionary detailing the preferable and/or required values or ranges of values for the track's constrainable properties. If you specify constraints, an audio track meeting the constraints is required.

## Examples

For browsers with [Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy) enabled, the samples below need the `microphone` feature enabled. See [Security](../mediadevices/getusermedia#security) in [MediaDevices.getUserMedia()](../mediadevices/getusermedia) for details and examples on how to configure this.

### Using a Boolean value

In this example, we provide a simple value of `true` for the `audio` property. This tells `getUserMedia()` that we require an audio track, but we don't care about any specifics beyond that.

    document.getElementById("startButton").addEventListener("click", function() {
      navigator.mediaDevices.getUserMedia({
        audio: true
      }).then(stream => audioElement.srcObject = stream)
        .catch(err => log(err.name + ": " + err.message));
    }, false);

Here we see an event handler for a <span class="page-not-created">`click`</span> event which uses [`getUserMedia()`](../mediadevices/getusermedia) to obtain an audio-only stream with no specific constraints, then attaches the resulting stream to an [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) element once the stream is returned.

#### Result

### Using a MediaTrackConstraints object

Now let's look at a similar example that uses a set of constraints based on the [`MediaTrackConstraints`](../mediatrackconstraints) dictionary:

    document.getElementById("startButton").addEventListener("click", function() {
      navigator.mediaDevices.getUserMedia({
        audio: {
          sampleSize: 8,
          echoCancellation: true
        }
      }).then(stream => audioElement.srcObject = stream)
        .catch(err => log(err.name + ": " + err.message));
    }, false);

Here we see an event handler for a [`click`](../element/click_event) event which calls [`getUserMedia()`](../mediadevices/getusermedia), specifying a set of audio constraints requesting that echo cancellation be enabled and that, if possible, the sample rate be 8 bits per sample instead of the more common 16 bits (possibly as a bandwidth saving measure). As long as an audio input device is available and the user allows it to be used, an audio track will be included in the resulting stream, and it will match the specified constraints as well as possible.

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamconstraints-audio">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamConstraints.audio' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

## See also

- [Media Capture and Streams API](../media_streams_api)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)
- [`MediaDevices.getUserMedia()`](../mediadevices/getusermedia)
- [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
- [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)
- [`MediaTrackConstraints`](../mediatrackconstraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints/audio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints/audio</a>

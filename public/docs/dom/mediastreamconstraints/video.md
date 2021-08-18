MediaStreamConstraints.video
============================

The [`MediaStreamConstraints`](../mediastreamconstraints) dictionary's `video` property is used to indicate what kind of video track, if any, should be included in the [`MediaStream`](../mediastream) returned by a call to [`getUserMedia()`](../mediadevices/getusermedia).

To learn more about how constraints work, see [Capabilities, constraints, and settings](../media_streams_api/constraints).

Syntax
------

    var videoConstraints = true | false | MediaTrackConstraints;

### Value

The value of the `video` property can be specified as either of two types:

[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)  
If a Boolean value is specified, it indicates whether or not a video track should be included in the returned stream; if it's `true`, a video track is included; if no video source is available or if permission is not given to use the video source, the call to `getUserMedia()` will fail. If `false`, no video track is included.

[`MediaTrackConstraints`](../mediatrackconstraints)  
A constraints dictionary detailing the preferable and/or required values or ranges of values for the track's constrainable properties. If you specify constraints, a video track meeting these constraints is required.

Examples
--------

### Using a Boolean value

In this example, we provide a simple value of `true` for the `video` property. This tells `getUserMedia()` that we require a video track, but we don't care about any specifics beyond that.

    document.getElementById("startButton").addEventListener("click", function() {
      navigator.mediaDevices.getUserMedia({
          video: true
      }).then(stream => videoElement.srcObject = stream)
        .catch(err => log(err.name + ": " + err.message));
    }, false);

Here we see an event handler for a <span class="page-not-created">`click`</span> event which uses [`getUserMedia()`](../mediadevices/getusermedia) to obtain a video-only stream with no specific constraints, then attaches the resulting stream to a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element once the stream is returned.

#### Result

### Using a MediaTrackConstraints object

Now let's look at a similar example that uses a set of constraints based on the [`MediaTrackConstraints`](../mediatrackconstraints) dictionary:

    document.getElementById("startButton").addEventListener("click", function() {
      navigator.mediaDevices.getUserMedia({
          video: {
            width: 160,
            height: 120,
            frameRate: 15
          }
      }).then(stream => videoElement.srcObject = stream)
        .catch(err => log(err.name + ": " + err.message));
    }, false);

Here we see an event handler for a <span class="page-not-created">`click`</span> event which calls [`getUserMedia()`](../mediadevices/getusermedia), specifying a set of video constraints that indicate a preference for a video track whose dimensions are as close as possible to 160x120 pixels, and whose frame rate is as close to 15 frames per second as possible. As long as a video input device is available and the user allows it to be used, a video track will be included in the resulting stream, and it will match the specified constraints as well as possible.

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamconstraints-video">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStreamConstraints.video' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

-   [Media Capture and Streams API](../media_streams_api)
-   [Capabilities, constraints, and settings](../media_streams_api/constraints)
-   [`MediaDevices.getUserMedia()`](../mediadevices/getusermedia)
-   [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
-   [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)
-   [`MediaTrackConstraints`](../mediatrackconstraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints/video" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamConstraints/video</a>

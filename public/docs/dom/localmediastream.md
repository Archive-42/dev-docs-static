# LocalMediaStream

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `LocalMediaStream` interface was part of the [Media Capture and Streams API](media_streams_api), representing a stream of data being generated locally (such as by [`getUserMedia()`](mediadevices/getusermedia). However, `getUserMedia()` now returns a [`MediaStream`](mediastream) instead, and this interface has been removed from the specification.

**Warning:** This interface is no longer available in any mainstream browser. Do not use `LocalMediaStream`; you need to update any code that does use it as soon as possible or your content or application will stop working. See [Stopping a video stream](mediastreamtrack#stopping_a_video_stream) in [MediaStreamTrack](mediastreamtrack) to learn how. All other functionality is found in [`MediaStream`](mediastream).

The primary reason for this interface to exist was to add a `stop()` method to its [`MediaStream`](mediastream) parent interface. However, control over playback of media has been moved to the individual [`MediaStreamTrack`](mediastreamtrack) objects, so this is no longer necessary. Instead, media is stopped by calling [`MediaStreamTrack.stop()`](mediastreamtrack/stop) on each track that needs to be stopped. The example for `MediaStreamTrack.stop()` demonstrates how to stop a multi-track stream, which is what `LocalMediaStream.stop()` used to be used for.

## Methods

`LocalMediaStream.stop()`  
Stops the stream. When the source of the stream is a connected device (such as a camera or microphone), capture of media from the device is halted. This method is no longer available with the deprecation of `LocalMediaStream`. See [Stopping a video stream](mediastreamtrack#stopping_a_video_stream) in [MediaStreamTrack](mediastreamtrack) to learn how to stop an entire stream.

## Specifications

Not part of any specification. This interface was previously part of [Media Capture and Streams](https://w3c.github.io/mediacapture-main/) but was removed in 2013.

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

`LocalMediaStream`

No

?

17-64

No

No

No

No

No

Yes-64

No

No

No

## See also

- [Media Capture and Streams API](media_streams_api)
- [`MediaStreamTrack.stop()`](mediastreamtrack/stop)
- [`getUserMedia()`](mediadevices/getusermedia)
- [`Navigator.getUserMedia()`](navigator/getusermedia), the old, callback-based version of `getUserMedia()`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LocalMediaStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LocalMediaStream</a>

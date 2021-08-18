# MediaDevices.getDisplayMedia()

The [`MediaDevices`](../mediadevices) interface's `getDisplayMedia()` method prompts the user to select and grant permission to capture the contents of a display or portion thereof (such as a window) as a [`MediaStream`](../mediastream). The resulting stream can then be recorded using the [MediaStream Recording API](../mediastream_recording_api) or transmitted as part of a [WebRTC](../webrtc_api) session.

See [Using the Screen Capture API](../screen_capture_api/using_screen_capture) for more details and an example.

## Syntax

    var promise = navigator.mediaDevices.getDisplayMedia(constraints);

### Parameters

`constraints` <span class="badge inline optional">Optional</span>  
An optional [`MediaStreamConstraints`](../mediastreamconstraints) object specifying requirements for the returned [`MediaStream`](../mediastream). Since `getDisplayMedia()` requires a video track, the returned stream will have one even if no video track is expressly requested by the `constraints` object.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`MediaStream`](../mediastream) containing a video track whose contents come from a user-selected screen area, as well as an optional audio track.

**Note:** Browser support for audio tracks varies, both in terms of whether or not they're supported at all by the media recorder and in terms of the which audio source or sourcoes are supported. Check the [compatibility table](#browser%0A____compatibility) for details for each browser.

### Exceptions

Rejections of the returned promise are made by passing a [`DOMException`](../domexception) error object to the promise's failure handler. Possible errors are:

<span class="page-not-created">`AbortError`</span>  
An error or failure that doesn't match any of the other exceptions below occurred.

<span class="page-not-created">`InvalidStateError`</span>  
The call to `getDisplayMedia()` was not made from code running due to a user action, such as an event handler. Another potential cause for this event: the [`document`](../document) in whose context `getDisplayMedia()` was called is not fully active; for example, perhaps it is not the frontmost tab.

<span class="page-not-created">`NotAllowedError`</span>  
Permission to access a screen area was denied by the user, or the current browsing instance is not permitted access to screen sharing.

<span class="page-not-created">`NotFoundError`</span>  
No sources of screen video are available for capture.

<span class="page-not-created">`NotReadableError`</span>  
The user selected a screen, window, tab, or other source of screen data, but a hardware or operating system level error or lockout occurred, preventing the sharing of the selected source.

<span class="page-not-created">`OverconstrainedError`</span>  
After creating the stream, applying the specified `constraints` fails because no compatible stream could be generated.

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
The specified `constraints` include constraints which are not permitted when calling `getDisplayMedia()`. These unsupported constraints are `advanced` and any constraints which in turn have a member named `min` or `exact`.

## Usage notes

### Privacy and security

Because `getDisplayMedia()` could be used in nefarious ways, it can be a source of significant privacy and security concerns. For that reason, the specification details measures browsers are required to take in order to fully support `getDisplayMedia()`.

- The specified `constraints` can't be used to limit the options available to the user. Instead, they must be applied after the user chooses a source, in order to generate output that matches the constraints.
- The go-ahead permission to use `getDisplayMedia()` cannot be persisted for reuse. The user must be prompted for permission every time.
- The call to `getDisplayMedia()` must be made from code which is running in response to a user action, such as in an event handler.
- Browsers are encouraged to provide a warning to users about sharing displays or windows that contain browsers, and to keep a close eye on what other content might be getting captured and shown to other users.

## Example

In the example below, a `startCapture()` method is created which initiates screen capture given a set of options specified by the `displayMediaOptions` parameter. The options are specified in the form of a [`MediaStreamConstraints`](../mediastreamconstraints) object which specifies the preferred stream configuration and the [display surface](../screen_capture_api/using_screen_capture#visible_vs_logical_display_surfaces) from which video is to be captured.

    async function startCapture(displayMediaOptions) {
      let captureStream = null;

      try {
        captureStream = await navigator.mediaDevices.getDisplayMedia(displayMediaOptions);
      } catch(err) {
        console.error("Error: " + err);
      }
      return captureStream;
    }

This uses <span class="page-not-created">`await`</span> to asynchronously wait for `getDisplayMedia()` to resolve with a [`MediaStream`](../mediastream) which contains the display contents as requested by the specified options. The stream is then returned to the caller for use, perhaps for adding to a WebRTC call using [`RTCPeerConnection.addTrack()`](../rtcpeerconnection/addtrack) to add the video track from the stream.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-mediadevices-getdisplaymedia">Screen Capture<br />
<span class="small">The definition of 'MediaDevices.getDisplayMedia()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`getDisplayMedia`

72

79

17

Available as a member of `Navigator` instead of `MediaDevices`.

66

33-66

Since Firefox 33 you can capture screen data using `getUserMedia()`, with a `video` constraint called `mediaSource`. Prior to 52 it relied on a client-configurable list of allowed sites.

No

60

13

No

API is available, but will always fail with `NotAllowedError`.

No

No

API is available, but will always fail with `NotAllowedError`.

No

No

No

`audio-capture-support`

74

On Windows and Chrome OS the entire system audio can be captured, but on Linux and Mac only the audio of a tab can be captured.

≤79

On Windows, the entire system audio can be captured, but on Linux and Mac only the audio of a tab can be captured.

No

No

?

No

No

No

No

No

No

No

## See also

- [Screen Capture API](../screen_capture_api)
- [Using the Screen Capture API](../screen_capture_api/using_screen_capture)
- [Media Capture and Streams API](../media_streams_api)
- [WebRTC API](../webrtc_api)
- [`getUserMedia()`](getusermedia): Capturing media from a camera and/or microphone

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getDisplayMedia</a>

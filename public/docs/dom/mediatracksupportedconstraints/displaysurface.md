# MediaTrackSupportedConstraints.displaySurface

The [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints) dictionary's `displaySurface` property indicates whether or not the [`displaySurface`](../mediatrackconstraints/displaysurface) constraint is supported by the user agent and the device on which the content is being used.

The supported constraints list is obtained by calling [`navigator.mediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints).

## Syntax

    isDisplaySurfaceSupported = supportedConstraints.displaySurface;

### Value

A Boolean value which is `true` if the [`displaySurface`](../mediatrackconstraints/displaysurface) constraint is supported by the device and user agent.

## Example

This method sets up the constraints object specifying the options for the call to [`getDisplayMedia()`](../mediadevices/getdisplaymedia). It adds the `displaySurface` constraint (requesting that only full-screen sharing be allowed) only if it is known to be supported by the browser. Capturing is then started by calling `getDisplayMedia()` and attaching the returned stream to the video element referenced by the variable `videoElem`.

    async function capture() {
      let supportedConstraints = navigator.mediaDevices.getSupportedConstraints();
      let displayMediaOptions = {
        video: {
        },
        audio: false;
      };

      if (supportedConstraints.displaySurface) {
        displayMediaOptions.video.displaySurface = "monitor";
      }

      try {
        videoElem.srcObject = await navigator.mediaDevices.getDisplayMedia(displayMediaOptions);
      } catch(err) {
        /* handle the error */
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-screen-share/#dom-mediatracksupportedconstraints-displaysurface">Screen Capture<br />
<span class="small">The definition of 'MediaTrackSupportedConstraints.displaySurface' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`displaySurface`

No

No

No

No

Yes

?

No

No

No

?

?

No

## See also

- [Screen Capture API](../screen_capture_api)
- [Using the screen capture API](../screen_capture_api/using_screen_capture)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)
- [`MediaDevices.getDisplayMedia()`](../mediadevices/getdisplaymedia)
- [`MediaStreamTrack.getConstraints()`](../mediastreamtrack/getconstraints)
- [`MediaStreamTrack.applyConstraints()`](../mediastreamtrack/applyconstraints)
- [`MediaStreamTrack.getSettings()`](../mediastreamtrack/getsettings)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/displaySurface" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackSupportedConstraints/displaySurface</a>

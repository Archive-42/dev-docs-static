# MediaStreamTrack.applyConstraints()

The ` applyConstraints``() ` method of the [`MediaStreamTrack`](../mediastreamtrack) interface applies a set of constraints to the track; these constraints let the Web site or app establish ideal values and acceptable ranges of values for the constrainable properties of the track, such as frame rate, dimensions, echo cancelation, and so forth.

Constraints can be used to ensure that the media meets certain guidelines you prefer. For example, you may prefer high-density video but require that the frame rate be a little low to help keep the data rate low enough not overtax the network. Constraints can also specify ideal and/or acceptable sizes or ranges of sizes. See [Applying constraints](../media_streams_api/constraints#applying_constraints) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for more information on how to apply your preferred constraints.

## Syntax

    const appliedPromise = track.applyConstraints([constraints])

### Parameters

`constraints` <span class="badge inline optional">Optional</span>  
A [`MediaTrackConstraints`](../mediatrackconstraints) object listing the constraints to apply to the track's constrainable properties; any existing constraints are replaced with the new values specified, and any constrainable properties not included are restored to their default constraints. If this parameter is omitted, all currently set custom constraints are cleared. This object represents the basic set of constraints that must apply for the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to resolve. The object may contain an advanced property containing an array of additional `MediaTrackConstraints` objects, which are treated as exact requires.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves when the constraints have been successfully applied. If the constraints cannot be applied, the promise is rejected with a <span class="page-not-created">`MediaStreamError`</span> whose name is `OverconstrainedError`, to indicate that the constraints could not be met. This can happen if the specified constraints are too strict to find a match when attempting to configure the track.

## Examples

The following shows how to specify a basic and advanced set of constraints. It specifies that the page or web app needs a width between 640 and 1280 and a height between 480 and 720, with the later number in each pair being preferred. The advanced property further specifies that an image size of 1920 by 1280 is the preferred or an aspect ratio of 1.333 if that is not available. Note that these constraints also illustrate what the spec refers to as a _backoff strategy_.

    const constraints = {
      width: {min: 640, ideal: 1280},
      height: {min: 480, ideal: 720},
      advanced: [
        {width: 1920, height: 1280},
        {aspectRatio: 1.333}
      ]
    };

    navigator.mediaDevices.getUserMedia({ video: true })
    .then(mediaStream => {
      const track = mediaStream.getVideoTracks()[0];
      track.applyConstraints(constraints)
      .then(() => {
        // Do something with the track such as using the Image Capture API.
      })
      .catch(e => {
        // The constraints could not be satisfied by the available devices.
      });
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatrackconstraints">Media Capture and Streams<br />
<span class="small">The definition of 'applyConstraints()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/mediacapture-image/#mediatrackconstraintset-section">MediaStream Image Capture<br />
<span class="small">The definition of 'applyConstraints()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds image constraints.</td></tr></tbody></table>

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

`applyConstraints`

63

12

50

No

46

11

63

63

50

43

11

7.0

## See also

- [MediaStream Image Capture API](../mediastream_image_capture_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/applyConstraints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/applyConstraints</a>

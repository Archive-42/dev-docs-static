# MediaStreamTrack.getConstraints()

The `getConstraints()` method of the [`MediaStreamTrack`](../mediastreamtrack) interface returns a [`MediaTrackConstraints`](../mediatrackconstraints) object containing the set of constraints most recently established for the track using a prior call to [`applyConstraints()`](applyconstraints). These constraints indicate values and ranges of values that the Web site or application has specified are required or acceptable for the included constrainable properties.

Constraints can be used to ensure that the media meets certain guidelines you prefer. For example, you may prefer high definition video but require that the frame rate be a little low to help keep the data rate low enough not overtax the network. Constraints can also specify ideal and/or acceptable sizes or ranges of sizes. See [Capabilities, constraints, and settings](../media_streams_api/constraints) for details on how to work with constrainable properties.

## Syntax

    const constraints = track.getConstraints()

### Return value

A [`MediaTrackConstraints`](../mediatrackconstraints) object which indicates the constrainable properties the Web site or app most recently set using [`applyConstraints()`](applyconstraints). The properties in the returned object are listed in the same order as when they were set, and only properties specifically set by the site or app are included.

**Note:** The returned set of constraints doesn't necessarily describe the actual state of the media. Even if any of the constraints couldn't be met, they are still included in the returned object as originally set by the site's code. To get the currently active settings for all constrainable properties, you should instead call [`getSettings()`](getsettings).

## Example

This example obtains the current constraints for a track, sets the [`facingMode`](../mediatrackconstraints/facingmode), and applies the updated constraints.

    function switchCameras(track, camera) {
      const constraints = track.getConstraints();
      constraints.facingMode = camera;
      track.applyConstraints(constraints);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-getconstraints">Media Capture and Streams<br />
<span class="small">The definition of 'getConstraints()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getConstraints`

53

12

50

No

Yes

11

53

52

50

Yes

11

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getConstraints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getConstraints</a>

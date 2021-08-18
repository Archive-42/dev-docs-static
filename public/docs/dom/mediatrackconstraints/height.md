# MediaTrackConstraints.height

The [`MediaTrackConstraints`](../mediatrackconstraints) dictionary's `height` property is a [`ConstrainULong`](../constrainulong) describing the requested or mandatory constraints placed upon the value of the [`height`](../mediatracksettings/height) constrainable property.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.height`](../mediatracksupportedconstraints/height) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

## Syntax

    var constraintsObject = { height: constraint };

    constraintsObject.height = constraint;

### Value

If this value is a number, the user agent will attempt to obtain media whose height is as close as possible to this number given the capabilities of the hardware and the other constraints specified. Otherwise, the value of this [`ConstrainULong`](../constrainulong) will guide the user agent in its efforts to provide an exact match to the required height (if `exact` is specified or both `min` and `max` are provided and have the same value) or to a best-possible value.

## Example

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatrackconstraintset-height">Media Capture and Streams<br />
<span class="small">The definition of 'height' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`height`

59

≤79

50

No

Yes

?

59

59

50

?

?

7.0

## See also

- [Media Capture and Streams API](../media_streams_api)
- [Capabilities, constraints, and settings](../media_streams_api/constraints)
- [`MediaTrackConstraints`](../mediatrackconstraints)
- [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
- [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)
- [`MediaStreamTrack`](../mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/height" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/height</a>

# MediaTrackControls.volume

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`MediaTrackConstraints`](../mediatrackconstraints) dictionary's `volume` property is a [`ConstrainDouble`](../constraindouble) describing the requested or mandatory constraints placed upon the value of the [`volume`](../mediatracksettings/volume) constrainable property.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.volume`](../mediatracksupportedconstraints/volume) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

## Syntax

    var constraintsObject = { volume: constraint };

    constraintsObject.volume = constraint;

### Value

A [`ConstrainDouble`](../constraindouble) describing the acceptable or required value(s) for an audio track's volume, on a linear scale where 0.0 means silence and 1.0 is the highest supported volume.

If this value is a number, the user agent will attempt to obtain media whose volume is as close as possible to this number given the capabilities of the hardware and the other constraints specified. Otherwise, the value of this [`ConstrainDouble`](../constraindouble) will guide the user agent in its efforts to provide an exact match to the required volume (if `exact` is specified or both `min` and `max` are provided and have the same value) or to a best-possible value.

Any constraint set which only permits values outside the range 0.0 to 1.0 cannot be satisfied and will result in failure.

## Example

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

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

`volume`

59

≤79

No

No

Yes

?

59

59

No

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/volume" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/volume</a>

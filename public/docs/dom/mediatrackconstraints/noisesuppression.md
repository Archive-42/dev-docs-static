MediaTrackConstraints.noiseSuppression
======================================

The [`MediaTrackConstraints`](../mediatrackconstraints) dictionary's `noiseSuppression` property is a [`ConstrainBoolean`](../constrainboolean) describing the requested or mandatory constraints placed upon the value of the [`noiseSuppression`](../mediatracksettings/noisesuppression) constrainable property.

If needed, you can determine whether or not this constraint is supported by checking the value of [`MediaTrackSupportedConstraints.noiseSuppression`](../mediatracksupportedconstraints/noisesuppression) as returned by a call to [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints). However, typically this is unnecessary since browsers will ignore any constraints they're unfamiliar with.

Noise suppression is typically provided by microphones, although it can be provided by other input sources as well.

Syntax
------

    var constraintsObject = { noiseSuppression: constraint };

    constraintsObject.noiseSuppression = constraint;

### Value

If this value is a simple `true` or `false`, the user agent will attempt to obtain media with noise suppression enabled or disabled as specified, if possible, but will not fail if this can't be done. If, instead, the value is given as an object with an `exact` field, that field's Boolean value indicates a required setting for the noise suppression feature; if it can't be met, then the request will result in an error.

Example
-------

See [Example: Constraint exerciser](#) in [Capabilities, constraints, and settings](../media_streams_api/constraints) for an example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediatrackconstraintset-noisesuppression">Media Capture and Streams<br />
<span class="small">The definition of 'noiseSuppression' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`noiseSuppression`

Yes

≤79

55

46

No

Yes

?

Yes

Yes

55

46

?

?

Yes

See also
--------

-   [Media Capture and Streams API](../media_streams_api)
-   [Capabilities, constraints, and settings](../media_streams_api/constraints)
-   [`MediaTrackConstraints`](../mediatrackconstraints)
-   [`MediaDevices.getSupportedConstraints()`](../mediadevices/getsupportedconstraints)
-   [`MediaTrackSupportedConstraints`](../mediatracksupportedconstraints)
-   [`MediaStreamTrack`](../mediastreamtrack)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/noiseSuppression" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaTrackConstraints/noiseSuppression</a>

# ConstrainBoolean

The `ConstrainBoolean` dictionary is used to specify a constraint for a property whose value is a Boolean value. You can specify an exact value which must be matched, an ideal value that should be matched if at all possible, and a fallback value to attempt to match once all more specific constraints have been applied.

## Properties

`exact`  
A Boolean which indicates a value the property must have.

`ideal`  
A Boolean value indicating the ideal, but not required, value the property should ideally have. If possible, this value will be used, but the user agent will use the other value if it needs to in order to come up with a workable configuration.

You can also specify the value of the property as `true` or `false`, in which case the user agent will use that value if possible once all efforts have been made to match the `exact` and `ideal` values for other properties.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-constrainboolean">Media Capture and Streams<br />
<span class="small">The definition of 'ConstrainBoolean' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Technically, `ConstrainBoolean` is actually based on an intermediary dictionary named `ConstrainBooleanParameters`, which adds `exact` and `ideal` to the simple Boolean type. However, for the sake of documentation clarity, the intermediate type (present only because of quirks in [WebIDL](https://developer.mozilla.org/en-US/docs/Glossary/WebIDL) syntax) is ignored here.

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

`ConstrainBoolean`

Yes

≤79

50

No

Yes

?

Yes

Yes

50

Yes

?

Yes

## See also

- [Media Capture and Streams API](media_streams_api)
- [Capabilities, constraints, and settings](media_streams_api/constraints)
- [`MediaTrackConstraints`](mediatrackconstraints)
- <span class="page-not-created">`MediaTrackCapabilities`</span>
- [`MediaTrackSupportedConstraints`](mediatracksupportedconstraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ConstrainBoolean" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ConstrainBoolean</a>

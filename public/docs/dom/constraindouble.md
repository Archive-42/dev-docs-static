# ConstrainDouble

The `ConstrainDouble` type is used to specify a constraint for a property whose value is a double-precision floating-point number. It extends the [`DoubleRange`](doublerange) dictionary (which provides the ability to specify a permitted range of property values) to also support an exact value and/or an ideal value the property should take on. Additionally, you can specify the property's value as a simple floating-point value, in which case the user agent does its best to match the value once all other more stringent constraints are met.

## Properties

_If the value of a `ConstrainDouble` is an object rather than a number, it may have the properties below in addition the properties it inherits from [`DoubleRange`](doublerange)._

`exact`  
A double-precision floating-point number specifying a specific, required, value the property must have to be considered acceptable.

`ideal`  
A double-precision floating-point number specifying a value the property would ideally have, but which can be considered optional if necessary to find a match.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-constraindouble">Media Capture and Streams<br />
<span class="small">The definition of 'ConstrainDouble' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Technically, `ConstrainDouble` is actually based on an intermediary dictionary named `ConstrainDoubleRange`, which adds `exact` and `ideal` to [`DoubleRange`](doublerange), with `ConstrainDouble` being a type that can be either a long integer or a `DoubleRange`. However, for the sake of documentation clarity, the intermediate type (present only because of quirks in [WebIDL](https://developer.mozilla.org/en-US/docs/Glossary/WebIDL) syntax) is ignored here.

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

`ConstrainDouble`

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
- [`DoubleRange`](doublerange)
- [`MediaTrackConstraints`](mediatrackconstraints)
- <span class="page-not-created">`MediaTrackCapabilities`</span>
- [`MediaTrackSupportedConstraints`](mediatracksupportedconstraints)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDouble" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDouble</a>

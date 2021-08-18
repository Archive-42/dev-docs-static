# ConstrainDOMString

The `ConstrainDOMString` dictionary is used to specify a constraint for a property whose value is a string. It allows you to specify one or more `exact` string values from which one must be the parameter's value, or a set of `ideal` values which should be used if possible. You can also specify a single string (or an array of strings) which the user agent will do its best to match once all more stringent constraints have been applied.

## Properties

The value of a `ConstrainDOMString` can be any of the following:

- A single [`DOMString`](domstring)
- An array of [`DOMString`](domstring) objects
- An object with one or both of the following properties:

`exact`  
Either a single [`DOMString`](domstring) which must be the value of the property, or an array of `DOMString` objects one of which must be the property's value. If the property can't be set to one of the listed values, matching will fail.

`ideal`  
Either a single [`DOMString`](domstring) or an array of `DOMString`s specifying ideal values for the property. If possible, one of the listed values will be used, but if it's not possible, the user agent will use the closest possible match.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-constraindomstring">Media Capture and Streams<br />
<span class="small">The definition of 'ConstrainDOMString' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

Technically, `ConstrainDOMString` is actually based on an intermediary dictionary named `ConstrainDOMStringParameters`, which adds `exact` and `ideal` to [`DOMString`](domstring). However, for the sake of documentation clarity, the intermediate type (present only because of quirks in [WebIDL](https://developer.mozilla.org/en-US/docs/Glossary/WebIDL) syntax) is ignored here.

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

`ConstrainDOMString`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDOMString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ConstrainDOMString</a>

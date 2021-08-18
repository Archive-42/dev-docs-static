# FeaturePolicy

The `FeaturePolicy` interface of the [Feature Policy API](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy) represents the set of policies applied to the current execution context.

## FeaturePolicy Methods

[`FeaturePolicy.allowsFeature`](featurepolicy/allowsfeature)  
Returns a Boolean that indicates whether or not a particular feature is enabled in the specified context.

[`FeaturePolicy.features`](featurepolicy/features)  
Returns a list of names of all features supported by the User Agent. Feature whose name appears on the list might not be allowed by the Feature Policy of the current execution context and/or might not be accessible because of user's permissions.

[`FeaturePolicy.allowedFeatures`](featurepolicy/allowedfeatures)  
Returns a list of names of all features supported by the User Agent and allowed by the Feature Policy. Note that features appearing on this list might still be behind a user permission.

[`FeaturePolicy.getAllowlistForFeature`](featurepolicy/getallowlistforfeature)  
Returns the Allow list for the specified feature.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/">Permissions Policy</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`FeaturePolicy`

74

73-74

69-73

79

65

No

62

60-62

56-60

No

74

74

73-74

69-73

65

48

No

11.0

`allowedFeatures`

74

69-73

79

65

No

62

56-62

No

74

74

69-74

65

48

No

11.0

`allowsFeature`

74

69-73

79

65

No

62

56-62

No

74

74

69-74

65

48

No

11.0

`features`

74

79

70

No

62

No

74

74

No

No

No

11.0

`getAllowlistForFeature`

74

69-73

79

65

No

62

56-62

No

74

74

69-74

65

48

No

11.0

## See also

- [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy)
- [Privacy, permissions, and information security](https://developer.mozilla.org/en-US/docs/Web/Privacy)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy</a>

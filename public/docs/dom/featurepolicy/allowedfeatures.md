# FeaturePolicy.allowedFeatures()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `allowedFeatures()` method of the [`FeaturePolicy`](../featurepolicy) interface returns a list of directive names of all features allowed by the feature policy.enables introspection of individual directives of the Feature Policy it is run on. As such, `allowedFeatures()` method returns a subset of directives returned by [`features()`](features).

## Syntax

    const allowed = FeaturePolicy.allowedFeatures()

### Parameters

None.

### Return value

An array of strings representing the Feature Policy directive names that are allowed by the Feature Policy this method is called on.

## Example

The following example logs all the allowed directives for the current document. Please note that these features might be restricted by the Permissions API, if the user did not grant the corresponding permission yet.

    // First, get the Feature Policy object
    const featurePolicy = document.featurePolicy

    // Then query feature for specific
    const allowed = featurePolicy.allowedFeatures()

    for (const directive of allowed){
      console.log(directive)
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/">Permissions Policy<br />
<span class="small">The definition of 'allowsFeature' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy/allowedFeatures" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy/allowedFeatures</a>

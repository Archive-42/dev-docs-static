FeaturePolicy.getAllowlistForFeature()
======================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getAllowlistForFeature()` method of the [`FeaturePolicy`](../featurepolicy) allows query of the allow list for a specific feature for the current Feature Policy.

Syntax
------

    const allowlist = FeaturePolicy.getAllowlistForFeature(<feature>)

### Parameter

#### Feature name

A specific feature name must be specified.

### Return value

An [Allow list](web/http/feature_policy/using_feature_policy) for the specified feature.

Errors
------

The function will raise a warning if the specified Feature Policy directive name is not known. However, it will also return empty array, indicating that no origin is allowed to use the feature.

Example
-------

The following example prints all the origins that are allowed to use Camera API by the Feature Policy. Please note that Camera API might be restricted by the Permissions API, if the user did not grant the corresponding permission yet.

    // First, get the Feature Policy object
    const featurePolicy = document.featurePolicy

    // Then query feature for specific
    const allowlist = featurePolicy.getAllowlistForFeature("camera")

    for (const origin of allowlist) {
      console.log(origin)
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/">Permissions Policy<br />
<span class="small">The definition of 'getAllowlistForFeature' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy/getAllowlistForFeature" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy/getAllowlistForFeature</a>

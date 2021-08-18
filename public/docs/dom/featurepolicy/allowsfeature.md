FeaturePolicy.allowsFeature()
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `allowsFeature()` method of the [`FeaturePolicy`](../featurepolicy) interface enables introspection of individual directives of the Feature Policy it is run on. It returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if and only if the specified feature is allowed in the specified context (or the default context if no context is specified).

Syntax
------

    const allowed = FeaturePolicy.allowsFeature(<feature>)

or

    const allowed = FeaturePolicy.allowsFeature(<feature>, <origin>)

### Parameters

#### `Feature name`

A specific feature name must be specified.

#### `Origin name` <span class="badge inline optional">Optional</span>

An origin URL to check the feature on. If it is omitted the default origin is used.

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if and only if the feature is allowed.

Example
-------

The following example queries whether or not the document is allowed to use camera API by the Feature Policy. Please note that Camera API might be restricted by the Permissions API, if the user did not grant the corresponding permission yet.

    // First, get the Feature Policy object
    const featurePolicy = document.featurePolicy

    // Then query feature for specific
    const allowed = featurePolicy.allowsFeature("camera")

    if (allowed){
      console.log("FP allows camera.")
    } else {
      console.log("FP does not allows camera.")
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/">Permissions Policy<br />
<span class="small">The definition of 'allowsFeature' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy/allowsFeature" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy/allowsFeature</a>

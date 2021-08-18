FeaturePolicy.features()
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `features()` method of the [`FeaturePolicy`](../featurepolicy) interface returns a list of names of all features supported by the User Agent. Feature whose name appears on the list might not be allowed by the Feature Policy of the current execution context and/or might not be accessible because of user's permissions.

Syntax
------

    const supportedFeatures = FeaturePolicy.features()

### Parameters

None.

### Return value

A list of strings that represent names of all Feature Policy directives supported by the User Agent.

Example
-------

The following example logs all the supported directives in the console.

    // Get the Feature Policy object
    const featurePolicy = document.featurePolicy

    // Retrieve the list of all supported Feature Policy directives
    const supportedDirectives = featurePolicy.features()

    // Print out each directive into the console
    for (const directive of supportedDirectives){
      console.log(directive)
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/">Permissions Policy<br />
<span class="small">The definition of 'features' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy/features" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FeaturePolicy/features</a>

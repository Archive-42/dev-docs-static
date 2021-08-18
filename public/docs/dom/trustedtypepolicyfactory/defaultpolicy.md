TrustedTypePolicyFactory.defaultPolicy
======================================

The `defaultPolicy` read-only property of the [`TrustedTypePolicyFactory`](../trustedtypepolicyfactory) interface returns the default [`TrustedTypePolicy`](../trustedtypepolicy) or null if this is empty.

**Note**

Information about the creation and use of default policies can be found in the `createPolicy()` documentation.

Syntax
------

    var defaultPolicy = TrustedTypePolicyFactory.defaultPolicy;

### Value

A [`TrustedTypePolicy`](../trustedtypepolicy) or null.

Examples
--------

The first line below returns null as no default policy has been created. Once a default policy is created, calling `defaultPolicy` returns that policy object.

    console.log(trustedTypes.defaultPolicy); // null
    const dp = trustedTypes.createPolicy('default', {});
    console.log(trustedTypes.defaultPolicy); // a TrustedTypePolicy object

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-defaultpolicy">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory.defaultPolicy' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`defaultPolicy`

83

83

No

No

69

No

83

83

No

59

No

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/defaultPolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/defaultPolicy</a>

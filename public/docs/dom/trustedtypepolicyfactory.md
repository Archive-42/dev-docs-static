TrustedTypePolicyFactory
========================

The `TrustedTypePolicyFactory` interface of the [`Trusted Types API`](trusted_types_api) creates policies and allows the verification of Trusted Type objects against created policies.

Properties
----------

 [`TrustedTypePolicyFactory.emptyHTML`](trustedtypepolicyfactory/emptyhtml)<span class="badge inline readonly">Read only </span>   
Returns a [`TrustedHTML`](trustedhtml) object containing an empty string.

 [`TrustedTypePolicyFactory.emptyScript`](trustedtypepolicyfactory/emptyscript)<span class="badge inline readonly">Read only </span>   
Returns a [`TrustedScript`](trustedscript) object containing an empty string.

 [`TrustedTypePolicyFactory.defaultPolicy`](trustedtypepolicyfactory/defaultpolicy)<span class="badge inline readonly">Read only </span>   
Returns the default [`TrustedTypePolicy`](trustedtypepolicy) or null if this is empty.

Methods
-------

[`TrustedTypePolicyFactory.createPolicy()`](trustedtypepolicyfactory/createpolicy)  
Creates a [`TrustedTypePolicy`](trustedtypepolicy) object that implements the rules passed as `policyOptions`.

[`TrustedTypePolicyFactory.isHTML()`](trustedtypepolicyfactory/ishtml)  
When passed a value checks that it is a valid [`TrustedHTML`](trustedhtml) object.

[`TrustedTypePolicyFactory.isScript()`](trustedtypepolicyfactory/isscript)  
When passed a value checks that it is a valid [`TrustedScript`](trustedscript) object.

[`TrustedTypePolicyFactory.isScriptURL()`](trustedtypepolicyfactory/isscripturl)  
When passed a value checks that it is a valid [`TrustedScriptURL`](trustedscripturl) object.

[`TrustedTypePolicyFactory.getAttributeType()`](trustedtypepolicyfactory/getattributetype)  
Allows web developers to check whether a Trusted Type is required for an element and attribute, and if so which one.

[`TrustedTypePolicyFactory.getPropertyType()`](trustedtypepolicyfactory/getpropertytype)  
Allows web developers to check whether a Trusted Type is required for a property, and if so which one.

Examples
--------

The below code creates a policy with the name `"myEscapePolicy"` with a function defined for `createHTML()` which sanitizes HTML.

We then use the policy to sanitize a string, creating a [`TrustedHTML`](trustedhtml) object, `escaped`. This object can be tested with [`isHTML()`](trustedtypepolicyfactory/ishtml) to ensure that it was created by one of our policies.

    const escapeHTMLPolicy = trustedTypes.createPolicy("myEscapePolicy", {
      createHTML: (string) => string.replace(/\>/g, "<")
    });

    const escaped = escapeHTMLPolicy.createHTML("<img src=x onerror=alert(1)>");

    console.log(trustedTypes.isHTML(escaped)) // true;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#trusted-type-policy-factory">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TrustedTypePolicyFactory`

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

`createPolicy`

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

`emptyHTML`

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

`emptyScript`

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

`getAttributeType`

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

`getPropertyType`

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

`isHTML`

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

`isScript`

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

`isScriptURL`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory</a>

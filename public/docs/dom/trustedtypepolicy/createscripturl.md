TrustedTypePolicy.createScriptURL()
===================================

The `createScriptURL()` method of the [`TrustedTypePolicy`](../trustedtypepolicy) interface creates a [`TrustedScriptURL`](../trustedscripturl) object using a policy created by [`TrustedTypePolicyFactory.createPolicy()`](../trustedtypepolicyfactory/createpolicy).

Syntax
------

    var str = TrustedTypePolicy.createScriptURL(input[,args]);

### Parameters

`input`  
A [`DOMString`](../domstring) containing the string to be sanitized by the policy.

 `args`<span class="badge inline optional">Optional</span>   
Additional arguments to be passed to the function represented by [`TrustedTypePolicy`](../trustedtypepolicy).

### Return value

A [`TrustedScriptURL`](../trustedscripturl) object.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if [`TrustedTypePolicy`](../trustedtypepolicy) does not contain a function to run on the input.

Examples
--------

In the below example a string containing the URL to an external resource is used as the input for `createScriptURL()`. The policy can check that this is an allowed URL before inserting it into an injection sink that could cause this external script to be executed.

    const escaped = escapeURLPolicy.createScriptURL("https://example.com/my-script.js");

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicy-createscripturl">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicy.createScriptURL()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`createScriptURL`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicy/createScriptURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicy/createScriptURL</a>

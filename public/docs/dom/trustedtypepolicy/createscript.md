TrustedTypePolicy.createScript()
================================

The `createScript()` method of the [`TrustedTypePolicy`](../trustedtypepolicy) interface creates a [`TrustedScript`](../trustedscript) object using a policy created by [`TrustedTypePolicyFactory.createPolicy()`](../trustedtypepolicyfactory/createpolicy).

Syntax
------

    var str = TrustedTypePolicy.createScript(input[,args]);

### Parameters

`input`  
A [`DOMString`](../domstring) containing the string to be sanitized by the policy.

 `args`<span class="badge inline optional">Optional</span>   
Additional arguments to be passed to the function represented by [`TrustedTypePolicy`](../trustedtypepolicy).

### Return value

A [`TrustedScript`](../trustedscript) object.

### Exceptions

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
Thrown if [`TrustedTypePolicy`](../trustedtypepolicy) does not contain a function to run on the input.

Examples
--------

In the below example a string containing a potentially risky script is used as the input for `createScript()`. The policy can sanitize this script before inserting it into an injection sink that could cause it to be executed.

    const sanitized = scriptPolicy.createScript("eval('2 + 2')");

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicy-createscript">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicy.createScript()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`createScript`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicy/createScript" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicy/createScript</a>

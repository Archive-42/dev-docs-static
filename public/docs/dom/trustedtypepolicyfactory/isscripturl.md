TrustedTypePolicyFactory.isScriptURL()
======================================

The `isScriptURL()` method of the [`TrustedTypePolicyFactory`](../trustedtypepolicyfactory) interface returns true if it is passed a valid [`TrustedScriptURL`](../trustedscripturl) object.

**Note:**

The purpose of the functions `isScriptURL()`, [`isHTML()`](ishtml), and [`isScript()`](isscript) is to check if the object is a valid TrustedType object, created by a configured policy.

Syntax
------

    var isScriptURL = TrustedTypePolicyFactory.isScriptURL(value);

### Parameters

`value`  
A [`TrustedScriptURL`](../trustedscripturl) object.

### Return value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)that is true if the object is a valid [`TrustedScriptURL`](../trustedscripturl) object.

Examples
--------

In the below example the constant `url` was created by a policy, and therefore `isScriptURL()` returns true. The second example is an attempt to fake an object, and the third is a string. Both of these will return false when passed to `isScriptURL()`.

    const url = policy.createScriptURL('https://example.com/myscript.js');
    console.log(trustedTypes.isScriptURL(url)) // true;

    const fake = Object.create(TrustedScriptURL.prototype);
    console.log(trustedTypes.isScriptURL(fake)); // false

    console.log(trustedTypes.isScriptURL("https://example.com/myscript.js")); // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-isscripturl">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory.isScriptURL()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/isScriptURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/isScriptURL</a>

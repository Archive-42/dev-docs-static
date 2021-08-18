TrustedTypePolicyFactory.isScript()
===================================

The `isScript()` method of the [`TrustedTypePolicyFactory`](../trustedtypepolicyfactory) interface returns true if it is passed a valid [`TrustedScript`](../trustedscript) object.

**Note:**

The purpose of the functions `isScript()`, [`isHTML()`](ishtml), and [`isScriptURL()`](isscripturl) is to check if the object is a valid TrustedType object, created by a configured policy.

Syntax
------

    var isScript = TrustedTypePolicyFactory.isScript(value);

### Parameters

`value`  
A [`TrustedScript`](../trustedscript) object.

### Return value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is true if the object is a valid [`TrustedScript`](../trustedscript) object.

Examples
--------

In the below example the constant `url` was created by a policy, and therefore `isScriptURL()` returns true. The second example is an attempt to fake an object, and the third is a string. Both of these will return false when passed to `isScriptURL()`.

    const myScript = policy.createScript("eval('2 + 2')");
    console.log(trustedTypes.isScript(myScript)) // true;

    const fake = Object.create(TrustedScript.prototype);
    console.log(trustedTypes.isScript(fake)); // false

    console.log(trustedTypes.isScript("eval('2 + 2')")); // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-isscript">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory.isScript()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/isScript" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/isScript</a>

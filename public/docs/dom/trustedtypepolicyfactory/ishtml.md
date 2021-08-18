TrustedTypePolicyFactory.isHTML()
=================================

The `isHTML()` method of the [`TrustedTypePolicyFactory`](../trustedtypepolicyfactory) interface returns true if it is passed a valid [`TrustedHTML`](../trustedhtml) object.

**Note:**

The purpose of the functions `isHTML()`, [`isScript()`](isscript), and [`isScriptURL()`](isscripturl) is to check if the object is a valid TrustedType object, created by a configured policy.

Syntax
------

    var isHTML = TrustedTypePolicyFactory.isHTML(value);

### Parameters

`value`  
A [`TrustedHTML`](../trustedhtml) object.

### Return value

A [`boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is true if the object is a valid [`TrustedHTML`](../trustedhtml) object.

Examples
--------

In the below example the constant `html` was created by a policy, and therefore `isHTML()` returns true. The second example is an attempt to fake an object, and the third is a string. Both of these will return false when passed to `isHTML()`.

    const html = policy.createHTML('<div>');
    console.log(trustedTypes.isHTML(html)) // true;

    const fake = Object.create(TrustedHTML.prototype);
    console.log(trustedTypes.isHTML(fake)); // false

    console.log(trustedTypes.isHTML("<div>plain string</div>")); // false

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-ishtml">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory.isHTML()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/isHTML" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/isHTML</a>

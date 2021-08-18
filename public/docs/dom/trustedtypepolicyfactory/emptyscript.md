TrustedTypePolicyFactory.emptyScript
====================================

The `emptyScript` read-only property of the [`TrustedTypePolicyFactory`](../trustedtypepolicyfactory) interface returns a [`TrustedScript`](../trustedscript) object containing an empty string.

This object can be used when the application requires an empty string to be inserted into an injection sink which is expecting a `TrustedScript` object.

Syntax
------

    var emptyScript = TrustedTypePolicyFactory.emptyScript;

### Value

A [`TrustedScript`](../trustedscript) object.

Examples
--------

The [specification](https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-emptyscript) explains that the `emptyScript` object can be used to detect support for dynamic code compilation.

Native Trusted Types implementations can support `eval(TrustedScript)`, therefore in the below example a native implementation will return false for `eval(trustedTypes.emptyScript)`. A polyfill will return a truthy object.

    const supportsTS = !eval(trustedTypes.emptyScript);
    eval(supportsTS ? myTrustedScriptObj : myTrustedScriptObj.toString());

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-emptyscript">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory.emptyScript' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/emptyScript" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/emptyScript</a>

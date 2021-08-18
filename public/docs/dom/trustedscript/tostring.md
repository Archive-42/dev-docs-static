TrustedScript.toString()
========================

The `toString()` method of the [`TrustedScript`](../trustedscript) interface returns a string which may safely inserted into an [injection sink](../trusted_types_api#injection_sinks).

Syntax
------

    var str = TrustedScript.toString();

### Return value

A [`string`](../domstring) containing the sanitized script.

Examples
--------

The constant `sanitized` is an object created via a Trusted Types policy. The `toString()` method returns a string to safely execute as a script.

    const sanitized = scriptPolicy.createScript("eval('2 + 2')");
    console.log(sanitized.toString());

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#trustedscript-stringification-behavior">Trusted Types<br />
<span class="small">The definition of 'TrustedScript.toString()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`toString`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedScript/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedScript/toString</a>

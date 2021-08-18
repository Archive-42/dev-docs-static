TrustedScript
=============

The `TrustedScript` interface of the [`Trusted Types API`](trusted_types_api) represents a string with an uncompiled script body that a developer can insert into an [injection sink](trusted_types_api#injection_sinks) that might execute the script. These objects are created via [`TrustedTypePolicy.createScript()`](trustedtypepolicy/createscript) and therefore have no constructor.

The value of a **TrustedScript** object is set when the object is created and cannot be changed by JavaScript as there is no setter exposed.

Methods
-------

[`TrustedScript.toJSON()`](trustedscript/tojson)  
Returns a JSON representation of the stored data.

[`TrustedScript.toString()`](trustedscript/tostring)  
A [`string`](domstring) containing the sanitized script.

Examples
--------

The constant `sanitized` is an object created via a Trusted Types policy.

    const sanitized = scriptPolicy.createScript("eval('2 + 2')");
    console.log(sanitized); /* a TrustedScript object */

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#trusted-script">Trusted Types<br />
<span class="small">The definition of 'TrustedScript' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TrustedScript`

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

See also
--------

-   [Prevent DOM-based cross-site scripting vulnerabilities with Trusted Types](https://web.dev/trusted-types/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedScript" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedScript</a>

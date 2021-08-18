TrustedScriptURL
================

The `TrustedScriptURL` interface of the [`Trusted Types API`](trusted_types_api) represents a string that a developer can insert into an [injection sink](trusted_types_api#injection_sinks) that will parse it as a URL of an external script. These objects are created via [`TrustedTypePolicy.createScriptURL()`](trustedtypepolicy/createscripturl) and therefore have no constructor.

The value of a **TrustedScriptURL** object is set when the object is created and cannot be changed by JavaScript as there is no setter exposed.

Methods
-------

[`TrustedScriptURL.toJSON()`](trustedscripturl/tojson)  
Returns a JSON representation of the stored data.

[`TrustedScriptURL.toString()`](trustedscripturl/tostring)  
A [`string`](usvstring) containing the sanitized URL.

Examples
--------

The constant `sanitized` is an object created via a Trusted Types policy.

    const sanitized = scriptPolicy.createScriptURL("https://example.com/my-script.js");
    console.log(sanitized;) /* a TrustedScriptURL object */

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#trused-script-url">Trusted Types<br />
<span class="small">The definition of 'TrustedScriptURL' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TrustedScriptURL`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedScriptURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedScriptURL</a>

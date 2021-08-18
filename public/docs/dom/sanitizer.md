Sanitizer
=========

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Sanitizer` interface of the [`HTML Sanitizer API`](html_sanitizer_api) allows developers to take untrusted strings of HTML, and sanitize them for safe insertion into a document’s DOM.

Constructors
------------

[`Sanitizer.Sanitizer`](sanitizer/sanitizer)  
Creates and returns a `Sanitizer` object.

Methods
-------

[`Sanitizer.sanitizeToString()`](sanitizer/sanitizetostring)  
Returns a sanitized [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) from an input, removing any offending elements or attributes.

[`Sanitizer.sanitize()`](sanitizer/sanitize)  
Returns a sanitized [`DocumentFragment`](documentfragment) from an input, removing any offending elements or attributes.

Examples
--------

This example shows the result of sanitizing a string using the [`Sanitizer.sanitizeToString()`](sanitizer/sanitizetostring) method. Disallowed `script` and `blink` elements are removed from the input.

    // our input string to clean
    const stringToClean = 'Some text <b><i>with</i></b> <blink>tags</blink>, including a rogue script <script>alert(1)</script> def.';

    const result = new Sanitizer().sanitizeToString(stringToClean);
    console.log(result);
    // Logs: "Some text <b><i>with</i></b> <blink>tags</blink>, including a rogue script def."

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/sanitizer-api/#sanitizer-api">HTML Sanitizer API<br />
<span class="small">The definition of 'sanitizer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Sanitizer`

No

No

83

No

No

No

No

No

83

No

No

No

`Sanitizer`

No

No

83

No

No

No

No

No

83

No

No

No

`sanitize`

No

No

83

No

No

No

No

No

83

No

No

No

`sanitizeToString`

No

No

83

No

No

No

No

No

83

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Sanitizer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Sanitizer</a>

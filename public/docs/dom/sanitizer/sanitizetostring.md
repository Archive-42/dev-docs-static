Sanitizer.sanitizeToString()
============================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `sanitizeToString()` method of the [`Sanitizer`](../sanitizer) interface returns a sanitized [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) from an input, removing any offending elements or attributes.

Syntax
------

    var String = sanitizer.sanitizeToString(input);

### Parameters

`input`  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) to be sanitized.

### Return value

A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

### Exceptions

None.

Examples
--------

This example uses the `sanitizeToString` method to remove disallowed `script` and `blink` elements from a string input.

    // our input string to clean
    const stringToClean = 'Some text <b><i>with</i></b> <blink>tags</blink>, including a rogue script <script>alert(1)</script> def.';

    const result = new Sanitizer().sanitizeToString(stringToClean);
    console.log(result);
    // Logs: "Some text <b><i>with</i></b> tags, including a rogue script def."

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/sanitizer-api/#sanitizer-api">HTML Sanitizer API<br />
<span class="small">The definition of 'sanitizeToString' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Sanitizer/sanitizeToString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Sanitizer/sanitizeToString</a>

Sanitizer.sanitize()
====================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `sanitize()` method of the [`sanitizer`](../sanitizer) interface returns a sanitized [`DocumentFragment`](../documentfragment) from an input, removing any offending elements or attributes.

Syntax
------

    var DocumentFragment = sanitizer.sanitize(input);

### Parameters

`input`  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) to be sanitized.

### Return value

A [`DocumentFragment`](../documentfragment).

### Exceptions

None.

Examples
--------

This example uses the `sanitize` method to remove a disallowed `script` and `blink` elements from a string input.

    // our input string to clean
    const stringToClean = 'Some text <b><i>with</i></b> <blink>tags</blink>, including a rogue script <script>alert(1)</script> def.';

    const result = new Sanitizer().sanitize(stringToClean);
    // Result: A DocumentFragment containing text nodes and a <b> element, with a <i> child element

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Sanitizer/sanitize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Sanitizer/sanitize</a>

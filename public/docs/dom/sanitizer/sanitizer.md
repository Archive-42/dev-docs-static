Sanitizer()
===========

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Sanitizer()` constructor creates a new [`sanitizer`](../sanitizer) object which allows developers to take untrusted strings of HTML, and sanitize them for safe insertion into a document’s DOM.

Syntax
------

    var sanitizer = new Sanitizer();

### Parameters

 `config` <span class="badge inline optional">Optional</span>   
An object in the format of SanitizerConfig. Options are as follows:

-   `allowElements`: An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representing elements the sanitizer should retain in the input.
-   `blockElements`: An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representing elements the sanitizer should remove in the input, but retain any of their children elements.
-   `dropElements`: An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representing elements the sanitizer should remove in the input along with their children.
-   `allowAttributes`: An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representing attributes the sanitizer should retain in the input.
-   `dropAttributes`: An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) representing attributes the sanitizer should remove in the input.

At the time of writing the default elements within each configuration property above are still under consideration. Due to this the above config parameter has not been implemented.

Examples
--------

This example shows the result of sanitizing a string with disallowed `script` elements.

    new Sanitizer().sanitizeToString("abc <script>alert(1)</script> def");
    // Result: script will be removed: "abc alert(1) def"

This example shows how the different configuration options would return the same string.

    const sample = "Some text <b><i>with</i></b> <blink>tags</blink>.";

    const allow = new Sanitizer({allowElements: [ "b" ]).sanitizeToString(sample);
    console.log(allow)
    // Logs: "Some text <b>with</b> text tags."

    const block = new Sanitizer({blockElements: [ "b" ]).sanitizeToString(sample);
    console.log(block);
    // Logs: "Some text <i>with</i> <blink>tags</blink>."

    const drop = new Sanitizer({dropElements: [ "b" ]).sanitizeToString(sample);
    // Logs: "Some text tags."

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Sanitizer/Sanitizer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Sanitizer/Sanitizer</a>

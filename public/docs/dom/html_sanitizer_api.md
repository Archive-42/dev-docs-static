# HTML Sanitizer API

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The HTML Sanitizer API allow developers to take untrusted strings of HTML, and sanitize them for safe insertion into a document’s DOM.

## Sanitizer API Concepts and Usage

Web applications often need to work with strings of HTML on the client side, perhaps as part of a client-side templating solution, perhaps as part of rendering user generated content. It is difficult to do so in a safe way. The Sanitizer API allows for rendering HTML in a safe manner.

To access the API you would use the constructor, which creates a [`Sanitizer.Sanitizer`](sanitizer/sanitizer) instance and allows for a configurable list of allowed or dis-allowed elements and attributes.

The most common use-case - preventing XSS - is handled by the built-in default lists, so that creating a [`Sanitizer.Sanitizer`](sanitizer/sanitizer) with a custom config is necessary only to handle additional, application-specific use cases.

The API has two methods to sanitize strings. One returns a string and the other returns a document fragment. See the [examples section below](#examples) for more.

## Sanitizer API Interfaces

[`Sanitizer`](sanitizer)  
The `Sanitizer` interface of the [`HTML Sanitizer API`](html_sanitizer_api) provides the functionality to take untrusted strings of HTML, and sanitize them for safe insertion into a document’s DOM.

## Examples

This example shows the result of sanitizing a string using the [`Sanitizer.sanitizeToString()`](sanitizer/sanitizetostring) method. A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) is returned with disallowed `script` and `blink` elements removed.

    // our input string to clean
    const stringToClean = 'Some text <b><i>with</i></b> <blink>tags</blink>, including a rogue script <script>alert(1)</script> def.';

    const result = new Sanitizer().sanitizeToString(stringToClean);
    console.log(result);
    // Logs: "Some text <b><i>with</i></b> <blink>tags</blink>, including a rogue script def."

The other method available is the [`Sanitizer.sanitize()`](sanitizer/sanitize) method. Which is very similar to above, however returns a [`DocumentFragment`](documentfragment) with disallowed `script` and `blink` elements removed.

    // our input string to clean
    const stringToClean = 'Some text <b><i>with</i></b> <blink>tags</blink>, including a rogue script <script>alert(1)</script> def.';

    const result = new Sanitizer().sanitize(stringToClean);
    // Result: A DocumentFragment containing text nodes and a <b> element, with a <i> child element

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/sanitizer-api/#sanitizer-api">HTML Sanitizer API<br />
<span class="small">The definition of 'sanitizeToString' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`HTML_Sanitizer_API`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTML_Sanitizer_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTML_Sanitizer_API</a>

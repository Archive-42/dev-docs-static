TrustedHTML.toString()
======================

The `toString()` method of the [`TrustedHTML`](../trustedhtml) interface returns a string which may safely inserted into an injection sink.

Syntax
------

    var str = TrustedHTML.toString();

### Return value

A [`string`](../domstring) containing the sanitized HTML.

Examples
--------

The constant `escaped` is an object created via the Trusted Types policy escapeHTMLPolicy. The `toString()` method returns a string to safely insert into a document.

    const escapeHTMLPolicy = trustedTypes.createPolicy("myEscapePolicy", {
      createHTML: (string) => string.replace(/\>/g, "<")
    });

    const escaped = escapeHTMLPolicy.createHTML("<img src=x onerror=alert(1)>");
    console.log(escaped.toString());

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#trustedhtml-stringification-behavior">Trusted Types<br />
<span class="small">The definition of 'TrustedHTML.toString()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedHTML/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedHTML/toString</a>

TrustedHTML
===========

The `TrustedHTML` interface of the [`Trusted Types API`](trusted_types_api) represents a string that a developer can insert into an [injection sink](trusted_types_api#injection_sinks) that will render it as HTML. These objects are created via [`TrustedTypePolicy.createHTML()`](trustedtypepolicy/createhtml) and therefore have no constructor.

The value of a **TrustedHTML** object is set when the object is created and cannot be changed by JavaScript as there is no setter exposed.

Methods
-------

[`TrustedHTML.toJSON()`](trustedhtml/tojson)  
Returns a JSON representation of the stored data.

[`TrustedHTML.toString()`](trustedhtml/tostring)  
A [`string`](domstring) containing the sanitized HTML.

Examples
--------

In the below example we create a policy that will create [`TrustedHTML`](trustedhtml) objects using [`TrustedTypePolicyFactory.createPolicy()`](trustedtypepolicyfactory/createpolicy). We can then use [`TrustedTypePolicy.createHTML`](trustedtypepolicy/createhtml) to create a sanitized HTML string to be inserted into the document.

The sanitized value can then be used with [`Element.innerHTML`](element/innerhtml) to ensure that no new HTML elements can be injected.

    <div id="myDiv"></div>

    const escapeHTMLPolicy = trustedTypes.createPolicy("myEscapePolicy", {
      createHTML: (string) => string.replace(/\>/g, "<")
    });

    let el = document.getElementById("myDiv");
    const escaped = escapeHTMLPolicy.createHTML("<img src=x onerror=alert(1)>");
    console.log(escaped instanceof TrustedHTML); // true
    el.innerHTML = escaped;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#trusted-html">Trusted Types<br />
<span class="small">The definition of 'TrustedHTML' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TrustedHTML`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedHTML" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedHTML</a>

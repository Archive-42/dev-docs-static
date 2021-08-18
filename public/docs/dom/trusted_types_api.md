Trusted Types API
=================

The **Trusted Types API** gives web developers a way to lock down the insecure parts of the [`DOM API`](document_object_model) to prevent client-side [Cross-site scripting](https://developer.mozilla.org/en-US/docs/Glossary/Cross-site_scripting) (XSS) attacks.

Concepts and Usage
------------------

Client-side, or DOM-based, XSS attacks happen when data controlled by a user (such as that input into a form field) reaches a function that can execute that data. These functions are known as *injection sinks*. DOM-based XSS attacks happen when a user is able to write arbitrary JavaScript code and have it executed by one of these functions.

The Trusted Types API locks down risky injection sinks, requiring you to process the data before passing it to one of these functions. If you use a string, then the browser will throw a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) and prevent the use of the function.

Trusted Types works alongside [Content-Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) with the [trusted-types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/trusted-types) and [require-trusted-types-for](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/require-trusted-types-for) directives.

### Injection Sinks

The Trusted Types API locks down injection sinks that can act as a vector for DOM-XSS attacks. An injection sink is any Web API function that should only be called with trusted, validated or santized input. Examples of injection sinks include:

-   Functions that insert HTML into the document such as [`Element.innerHTML`](element/innerhtml), [`Element.outerHTML`](element/outerhtml), or [`Document.write`](document/write).
-   Functions that create a new same-origin [`Document`](document) with caller-controlled markup such as [`DOMParser.parseFromString`](domparser/parsefromstring).
-   Functions that execute code such as [`Global_Objects/eval`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval).
-   Setters for [`Element`](element) attributes that accept a URL of code to load or execute.

Trusted Types will force you to process the data before passing it to any injection sink rather than use a string. This ensures that the data is trustworthy.

### Trusted Type Policies

A policy is a factory for Trusted Types. Web developers can specify a set of policies used for the creation of typed objects which form the trusted codebase for valid Trusted Type objects.

Interfaces
----------

[`TrustedHTML`](trustedhtml)  
Represents a string to insert into an injection sink that will render it as HTML.

[`TrustedScript`](trustedscript)  
Represents a string to insert into an injection sink that could lead to the script being executed.

[`TrustedScriptURL`](trustedscripturl)  
Represents a string to insert into an injection sink that will parse it as an URL of an external script resource.

[`TrustedTypePolicy`](trustedtypepolicy)  
Defines the functions used to create the above Trusted Type objects.

[`TrustedTypePolicyFactory`](trustedtypepolicyfactory)  
Creates policies and verifies that Trusted Type object instances were created via one of the policies.

<span class="page-not-created">`TrustedTypePolicyOptions`</span>  
A dictionary that holds author-defined functions for converting string values into trusted values.

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

Read more about this example, and discover other ways to sanitize input in the article [Prevent DOM-based cross-site scripting vulnerabilities with Trusted Types](https://web.dev/trusted-types/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/">Trusted Types</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

Polyfill
--------

A [polyfill is available](https://github.com/w3c/webappsec-trusted-types#polyfill). The polyfill is also available as an npm package [trusted-types](https://www.npmjs.com/package/trusted-types).

See also
--------

-   [Prevent DOM-based cross-site scripting vulnerabilities with Trusted Types](https://web.dev/trusted-types/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Trusted_Types_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Trusted_Types_API</a>

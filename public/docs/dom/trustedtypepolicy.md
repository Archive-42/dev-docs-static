TrustedTypePolicy
=================

The `TrustedTypePolicy` interface of the [`Trusted Types API`](trusted_types_api) defines a group of functions which create <span class="page-not-created">`TrustedType`</span> objects.

A `TrustedTypePolicy` object is created by [`TrustedTypePolicyFactory.createPolicy()`](trustedtypepolicyfactory/createpolicy) to define a policy for enforcing security rules on input. Therefore, `TrustedTypePolicy` has no constructor.

Properties
----------

 [`TrustedTypePolicy.name`](trustedtypepolicy/name)<span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) containing the name of the policy.

Methods
-------

[`TrustedTypePolicy.createHTML()`](trustedtypepolicy/createhtml)  
Creates a [`TrustedHTML`](trustedhtml) object.

[`TrustedTypePolicy.createScript()`](trustedtypepolicy/createscript)  
Creates a [`TrustedScript`](trustedscript) object.

[`TrustedTypePolicy.createScriptURL()`](trustedtypepolicy/createscripturl)  
Creates a [`TrustedScriptURL`](trustedscripturl) object.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#trustedtypepolicy">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicy' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TrustedTypePolicy`

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

`createHTML`

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

`createScript`

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

`createScriptURL`

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

`name`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicy</a>

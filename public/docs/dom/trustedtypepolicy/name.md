TrustedTypePolicy.name
======================

The `name` read-only property of the [`TrustedTypePolicy`](../trustedtypepolicy) interface returns the name of the policy.

Syntax
------

    var name = TrustedTypePolicy.name;

### Value

A [`DOMString`](../domstring) containing the name of the policy.

Examples
--------

In the below example a policy called `myEscapePolicy` is created using [`TrustedTypePolicyFactory.createPolicy()`](../trustedtypepolicyfactory/createpolicy) and is represented by the object `escapeHTMLPolicy`. Calling `name` on this object returns the string "myEscapePolicy".

    const escapeHTMLPolicy = trustedTypes.createPolicy("myEscapePolicy", {
      createHTML: (string) => string.replace(/\>/g, "<")
    });

    console.log(escapeHTMLPolicy.name); /* "myEscapePolicy" */

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicy-name">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicy.name' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicy/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicy/name</a>

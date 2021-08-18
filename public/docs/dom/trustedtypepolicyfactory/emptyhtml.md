TrustedTypePolicyFactory.emptyHTML
==================================

The `emptyHTML` read-only property of the [`TrustedTypePolicyFactory`](../trustedtypepolicyfactory) interface returns a [`TrustedHTML`](../trustedhtml) object containing an empty string.

This object can be used when the application requires an empty string to be inserted into an injection sink.

Syntax
------

    var emptyHTML = TrustedTypePolicyFactory.emptyHTML;

### Value

A [`TrustedHTML`](../trustedhtml) object.

Examples
--------

In the below example an empty string is to be inserted into the element. Therefore there is no need to create a policy, and the `emptyHTML` property can be used to insert the empty element when a Trusted Types object is expected.

    el.innerHTML = trustedTypes.emptyHTML;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-emptyhtml">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory.emptyHTML' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`emptyHTML`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/emptyHTML" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/emptyHTML</a>

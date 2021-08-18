TrustedTypePolicyFactory.getAttributeType()
===========================================

The `getAttributeType()` method of the [`TrustedTypePolicyFactory`](../trustedtypepolicyfactory) interface allows web developers to check if a Trusted Type is required for an element, and if so which Trusted Type is used.

Syntax
------

    var attributeType = TrustedTypePolicyFactory.getAttributeType(tagName,attribute[,elementNs,attrNs]);

### Parameters

`tagName`  
A [`string`](../domstring) containing the name of an HTML tag.

`attribute`  
A [`string`](../domstring) containing an attribute.

 `elementNs`<span class="badge inline optional">Optional</span>   
A [`string`](../domstring) containing a namespace, if empty defaults to the HTML namespace.

 `attrNs`<span class="badge inline optional">Optional</span>   
A [`string`](../domstring) containing a namespace, if empty defaults to null.

### Return value

A [`string`](../domstring) with one of:

-   `"TrustedHTML"`
-   `"TrustedScript"`
-   `"TrustedScriptURL"`

Or, null.

Examples
--------

In this example, passing the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element and [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-src) attribute to `getAttributeType` returns "TrustedScriptURL".

    console.log(trustedTypes.getAttributeType('script', 'src')); // "TrustedScriptURL"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-getattributetype">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory.getAttributeType()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getAttributeType`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/getAttributeType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/getAttributeType</a>

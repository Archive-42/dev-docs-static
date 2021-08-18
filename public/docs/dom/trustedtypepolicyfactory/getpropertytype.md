TrustedTypePolicyFactory.getPropertyType()
==========================================

The `getPropertyType()` method of the [`TrustedTypePolicyFactory`](../trustedtypepolicyfactory) interface allows web developers to check if a Trusted Type is required for an element's property.

Syntax
------

    var null = TrustedTypePolicyFactory.getPropertyType(tagName,property[, elementNS]);

### Parameters

`tagName`  
A [`string`](../domstring) containing the name of an HTML tag.

`property`  
A [`string`](../domstring) containing a property, for example `"innerHTML"`.

 `elementNs`<span class="badge inline optional">Optional</span>   
A [`string`](../domstring) containing a namespace, if empty defaults to the HTML namespace.

### Return value

A [`string`](../domstring) with one of:

-   `"TrustedHTML"`
-   `"TrustedScript"`
-   `"TrustedScriptURL"`

Or, null.

Examples
--------

In this example, passing the [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element and `innerHTML` property to `getPropertyType` returns "TrustedHTML".

    console.log(trustedTypes.getPropertyType('div', 'innerHTML')); // "TrustedHTML"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-trusted-types/dist/spec/#dom-trustedtypepolicyfactory-getpropertytype">Trusted Types<br />
<span class="small">The definition of 'TrustedTypePolicyFactory.getPropertyType()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getPropertyType`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/getPropertyType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TrustedTypePolicyFactory/getPropertyType</a>

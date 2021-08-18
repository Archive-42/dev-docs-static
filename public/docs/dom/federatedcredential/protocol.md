# FederatedCredential.protocol

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `protocol` property of the [`FederatedCredential`](../federatedcredential) interface returns a read-only [`DOMString`](../domstring) containing a credential's federated identity protocol. If this property is [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null), the protocol may be inferred from the [`FederatedCredential.provider`](provider) property.

## Syntax

    var protocol = FederatedCredential.protocol

### Value

A [`DOMString`](../domstring) containing a credential's federated identity protocol (e.g. `openidconnect`).

## Examples

    // TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/#dom-federatedcredential-protocol">Credential Management Level 1<br />
<span class="small">The definition of 'protocol' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`protocol`

51

79

No

No

38

No

51

51

No

41

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FederatedCredential/protocol" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FederatedCredential/protocol</a>

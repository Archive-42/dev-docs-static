# Credential

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `Credential` interface of the [Credential Management API](credential_management_api) provides information about an entity (usually a user) as a prerequisite to a trust decision.

`Credential` objects may be of 3 different types:

- [`PasswordCredential`](passwordcredential)
- [`PublicKeyCredential`](publickeycredential)
- [`FederatedCredential`](federatedcredential)

## Properties

[`Credential.id`](credential/id) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) containing the credential's identifier. This might be any one of a GUID, username, or email address.

[`Credential.type`](credential/type) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMString`](domstring) containing the credential's type. Valid values are `password`, `federated` and `public-key`. (For [`PasswordCredential`](passwordcredential), [`FederatedCredential`](federatedcredential) and [`PublicKeyCredential`](publickeycredential))

### Event handlers

None.

## Methods

None.

## Examples

    let pwdCredential = new PasswordCredential({
      id: "example-username", // Username/ID
      name: "John Doe", // Display name
      password: "correct horse battery staple" // Password
    });

    console.assert(pwdCredential.type === "password");

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/">Credential Management Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Credential`

51

18

60

No

38

13

51

51

60

41

13

5.0

`id`

51

18

60

No

38

13

51

51

60

41

13

5.0

`type`

51

18

60

No

38

13

51

51

60

41

13

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Credential" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Credential</a>

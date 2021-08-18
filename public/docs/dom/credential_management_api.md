# Credential Management API

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Credential Management API lets a website store and retrieve password, public key, and federated credentials. These capabilities allow users to sign in without typing passwords, see the federated account they used to sign in to a site, and resume a session without the explicit sign-in flow of an expired session.

## Credential management concepts and usage

This API lets websites interact with a user agent’s password system directly so that websites can deal in a uniform way with site credentials and user agents can provide better assistance with the management of their credentials. For example, user agents have a particularly hard time dealing with federated identity providers or esoteric sign-in mechanisms.

To address these problems, the Credential Management API provides ways for a website to store and retrieve different types of credentials. This gives users capabilities such as seeing the federated account they used to sign on to a site, or resuming a session without the explicit sign-in flow of an expired session.

This API is restricted to top-level contexts. Calls to `get()` and `store()` within an `<iframe>` element will resolve without effect.

### Subdomain-shared credentials

Later version of the spec allow credentials to be retrieved from a different subdomain. For example, a password stored in `login.example.com` may be used to log in to `www.example.com`. To take advantage of this, a password must be explicitly stored by calling [`CredentialsContainer.store()`](credentialscontainer/store). This is sometimes referred to as public suffix list (PSL) matching; however the spec only _recommends_ using PSL to determine the effective scope of a credential. It does not require it. Hence browsers may vary in their implementation.

## Interfaces

[`Credential`](credential)  
Provides information about an entity as a prerequisite to a trust decision.

[`CredentialsContainer`](credentialscontainer)  
Exposes methods to request credentials and notify the user agent when interesting events occur such as successful sign in or sign out. This interfaces is accessible from `navigator.credentials`.

[`FederatedCredential`](federatedcredential)  
Provides information about credentials from a federated identity provider, which is an entity that a website trusts to correctly authenticate a user, and which provides an API for that purpose. [OpenID Connect](https://openid.net/developers/specs/) is an example of such a framework.

[`PasswordCredential`](passwordcredential)  
Provides information about a username/password pair.

[`PublicKeyCredential`](publickeycredential)  
Provides a credential for logging in using a more secure system based on asymmetric cryptography instead of a password.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/">Credential Management Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webauthn/">Web Authentication: An API for accessing Public Key Credentials Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Credential_Management_API`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Credential_Management_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Credential_Management_API</a>

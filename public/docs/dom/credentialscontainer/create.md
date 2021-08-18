# CredentialsContainer.create()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `create()` method of the [`CredentialsContainer`](../credentialscontainer) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a new [`Credential`](../credential) instance based on the provided options, or `null` if no `Credential` object can be created.

This method is restricted to top-level contexts. Calls to it within an `<iframe>` element will resolve without effect.

## Syntax

    var promise = CredentialsContainer.create([options])

### Parameters

options  
An object of type <span class="page-not-created">`CredentialCreationOptions`</span> that contains options for the requested new `Credentials` object. It must include one of the options "password", "federated", or "publicKey". The options are:

- `password`: <span class="badge inline optional">Optional</span> Either an [`HTMLFormElement`](../htmlformelement), or a <span class="page-not-created">`PasswordCredentialData`</span> object. TBD
  - `id`: (required) [`USVString`](../usvstring) Inherited from <span class="page-not-created">`CredentialData`</span>.
  - `name`: <span class="badge inline optional">Optional</span> [`USVString`](../usvstring) TBD
  - `iconURL`: <span class="badge inline optional">Optional</span> [`USVString`](../usvstring) TBD
  - `password`: (required) [`USVString`](../usvstring) TBD
- `federated`: <span class="badge inline optional">Optional</span> An <span class="page-not-created">`FederatedCredentialInit`</span> object. Contains requirements for creating/obtaining federated credentials. The available options are:
  - `id`: (required) [`USVString`](../usvstring) Inherited from <span class="page-not-created">`CredentialData`</span>.
  - `name`: <span class="badge inline optional">Optional</span> [`USVString`](../usvstring) TBD
  - `iconURL`: <span class="badge inline optional">Optional</span> [`USVString`](../usvstring) TBD
  - `provider`: (required) [`USVString`](../usvstring) TBD
  - `protocol`: <span class="badge inline optional">Optional</span> [`USVString`](../usvstring) TBD
- `publicKey`: <span class="badge inline optional">Optional</span> an [`PublicKeyCredentialCreationOptions`](../publickeycredentialcreationoptions) object that describes the options for creating a [WebAuthn](../web_authentication_api) credential.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Credential`](../credential) instance, such as [`PasswordCredential`](../passwordcredential), [`FederatedCredential`](../federatedcredential), or [`PublicKeyCredential`](../publickeycredential).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/#dom-credentialscontainer-get">Credential Management Level 1<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webauthn/">Web Authentication: An API for accessing Public Key Credentials Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`create`

60

18

61

No

47

13

60

60

61

44

13

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer/create" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer/create</a>

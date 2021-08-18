# CredentialsContainer.get()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `get()` method of the [`CredentialsContainer`](../credentialscontainer) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to a single [`Credential`](../credential) instance that matches the provided parameters. If no match is found the Promise will resolve to null.

This method first collects all credentials in the [`CredentialsContainer`](../credentialscontainer) that meet the necessary criteria (defined in the `options` argument). From the resulting set of credentials, it then selects the best one. Depending on the options, it may display a dialog to the user and ask the user to make the selection.

This method collects credentials by calling the "CollectFromCredentialStore" method for each credential type allowed by the `options` argument. For example: if options.password exists, then the [`PasswordCredential`](../passwordcredential).\[\[CollectFromCredentialStore\]\] is called.

This method is restricted to top-level contexts. Calls to it within an `<iframe>` element will resolve without effect.

## Syntax

    var promise = CredentialsContainer.get([options])

### Parameters

options <span class="badge inline optional">Optional</span>  
An object of type <span class="page-not-created">`CredentialRequestOptions`</span> that contains options for the request. The options include criteria that the credentials are required or allowed to have, and options for interacting with the user. It can contain the following properties:

- `password`: a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating that returned [`Credential`](../credential) instances should include user (as opposed to federated) credentials.
- `federated`: A <span class="page-not-created">`FederatedCredentialRequestOptions`</span> object containing requirements for returned federated credentials. The available options are:
  - `providers`: An array of [`DOMString`](../domstring) instances of identity providers to search for.
  - `protocols` An array of [`DOMString`](../domstring) instances of federation protocols to search for.
- `publicKey`: An [`PublicKeyCredentialRequestOptions`](../publickeycredentialrequestoptions) object containing requirements for returned [WebAuthn](../web_authentication_api) credentials.
- `mediation`: A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) indicating whether the user will be required to log on for every visit to the website. Valid values are `"silent"`, `"optional"`, or `"required"`.
- `unmediated`: <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating the returned [`Credential`](../credential) instance should not require user mediation.
- `signal`: An instance of [`AbortSignal`](../abortsignal) that can indicate that an ongoing `get()` operation should be halted. An aborted operation may complete normally (generally if the abort was received after the operation finished) or reject with an "`AbortError`" [`DOMException`](../domexception).

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`Credential`](../credential) instance that matches the provided parameters. If a single Credential cannot be unambiguously obtained, the Promise will resolve to null.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/#dom-credentialscontainer-get">Credential Management Level 1<br />
<span class="small">The definition of 'get()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webauthn/">Web Authentication: An API for accessing Public Key Credentials Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

BCD tables only load in the browser

- [`Feature-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy) directive [`publickey-credentials-get`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/publickey-credentials-get)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer/get" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer/get</a>

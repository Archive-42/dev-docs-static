# PublicKeyCredential

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PublicKeyCredential` interface provides information about a public key / private key pair, which is a credential for logging in to a service using an un-phishable and data-breach resistant asymmetric key pair instead of a password. It inherits from [`Credential`](credential), and was created by the [Web Authentication API](web_authentication_api) extension to the [Credential Management API](credential_management_api). Other interfaces that inherit from [`Credential`](credential) are [`PasswordCredential`](passwordcredential) and [`FederatedCredential`](federatedcredential).

**Note:** This API is restricted to top-level contexts. Use from within an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) element will not have any effect.

## Properties

`PublicKeyCredential.type` <span class="badge inline readonly">Read only </span><span class="notecard inline secure">Secure context</span>  
Inherited from [`Credential`](credential). Always set to `public-key` for `PublicKeyCredential` instances.

[`PublicKeyCredential.id`](publickeycredential/id) <span class="badge inline readonly">Read only </span><span class="notecard inline secure">Secure context</span>  
Inherited from [`Credential`](credential) and overridden to be the [base64url encoding](https://developer.mozilla.org/en-US/docs/Glossary/Base64) of [`PublicKeyCredential.rawId`](publickeycredential/rawid).

[`PublicKeyCredential.rawId`](publickeycredential/rawid) <span class="badge inline readonly">Read only </span><span class="notecard inline secure">Secure context</span>  
An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) that holds the globally unique identifier for this `PublicKeyCredential`. This identifier can be used to look up credentials for future calls to [`CredentialsContainer.get`](credentialscontainer/get).

[`PublicKeyCredential.response`](publickeycredential/response) <span class="badge inline readonly">Read only </span> <span class="notecard inline secure">Secure context</span>  
An instance of an [`AuthenticatorResponse`](authenticatorresponse) object. It is either of type [`AuthenticatorAttestationResponse`](authenticatorattestationresponse) if the `PublicKeyCredential` was the results of a [`navigator.credentials.create()`](credentialscontainer/create) call, or of type [`AuthenticatorAssertionResponse`](authenticatorassertionresponse) if the `PublicKeyCredential` was the result of a [`navigator.credentials.get()`](credentialscontainer/get) call.

## Methods

[`PublicKeyCredential.getClientExtensionResults()`](publickeycredential/getclientextensionresults)<span class="notecard inline secure">Secure context</span>  
If any extensions were requested, this method will return the results of processing those extensions.

[`PublicKeyCredential.isUserVerifyingPlatformAuthenticatorAvailable()`](publickeycredential/isuserverifyingplatformauthenticatoravailable)<span class="notecard inline secure">Secure context</span>  
A static method returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to `true` if an authenticator bound to the platform is capable of _verifying_ the user.

## Examples

### Creating a new instance of PublicKeyCredential

Here, we use [`navigator.credentials.create()`](credentialscontainer/create) to generate a new credential.

    var publicKey = {
      challenge: /* from the server */,
      rp: {
        name: "Example CORP",
        id  : "login.example.com"
      },
      user: {
        id: new Uint8Array(16),
        name: "jdoe@example.com",
        displayName: "John Doe"
      },
      pubKeyCredParams: [
        {
          type: "public-key",
          alg: -7
        }
      ]
    };

    navigator.credentials.create({ publicKey })
      .then(function (newCredentialInfo) {
        var response = newCredentialInfo.response;
        var clientExtensionsResults = newCredentialInfo.getClientExtensionResults();
      }).catch(function (err) {
         console.error(err);
      });

### Getting an existing instance of PublicKeyCredential

Here, we fetch an existing credential from an authenticator, using [`navigator.credentials.get()`](credentialscontainer/get).

    var options = {
      challenge: new Uint8Array([/* bytes sent from the server */])
    };

    navigator.credentials.get({ "publicKey": options })
        .then(function (credentialInfoAssertion) {
        // send assertion response back to the server
        // to proceed with the control of the credential
    }).catch(function (err) {
         console.error(err);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#iface-pkcredential">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'PublicKeyCredential interface' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PublicKeyCredential`

67

18

60

Only supports USB U2F tokens.

No

No

13

No

70

60

Only supports USB U2F tokens.

No

13

No

`getClientExtensionResults`

67

18

60

Only supports USB U2F tokens.

No

No

13

No

70

60

Only supports USB U2F tokens.

No

13

No

`isUserVerifyingPlatformAuthenticatorAvailable`

67

18

60

Only supports USB U2F tokens.

No

No

13

No

70

60

Only supports USB U2F tokens.

No

13

No

`rawId`

67

18

60

Only supports USB U2F tokens.

No

No

13

No

70

60

Only supports USB U2F tokens.

No

13

No

`response`

67

18

60

Only supports USB U2F tokens.

No

No

13

No

70

60

Only supports USB U2F tokens.

No

13

No

## See also

- The parent interface [`Credential`](credential)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential</a>

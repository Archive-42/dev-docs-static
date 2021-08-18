# AuthenticatorAttestationResponse

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `AuthenticatorAttestationResponse` interface of the [Web Authentication API](web_authentication_api) is returned by [`CredentialsContainer.create()`](credentialscontainer/create) when a [`PublicKeyCredential`](publickeycredential) is passed, and provides a cryptographic root of trust for the new key pair that has been generated. This response should be sent to the relying party's server to complete the creation of the credential.

This interface inherites from [`AuthenticatorResponse`](authenticatorresponse).

**Note:** This interface is restricted to top-level contexts. Use from within an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) element will not have any effect.

## Properties

`AuthenticatorAttestationResponse.clientDataJSON` <span class="notecard inline secure">Secure context</span><span class="badge inline readonly">Read only </span>  
Client data for the authentication, such as origin and challenge. The [`clientDataJSON`](authenticatorresponse/clientdatajson) property is inherited from the [`AuthenticatorResponse`](authenticatorresponse).

[`AuthenticatorAttestationResponse.attestationObject`](authenticatorattestationresponse/attestationobject) <span class="notecard inline secure">Secure context</span><span class="badge inline readonly">Read only </span>  
An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing authenticator data and an attestation statement for a newly-created key pair.

## Methods

[`AuthenticatorAttestationResponse.getTransports()`](authenticatorattestationresponse/gettransports)<span class="notecard inline secure">Secure context</span>  
Returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of strings describing which transport methods (e.g. `usb`, `nfc`) are believed to be supported with the authenticator. The array may be empty if the information is not available.

## Examples

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
        // Do something with the response
        // (sending it back to the relying party server maybe?)
      }).catch(function (err) {
         console.error(err);
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#authenticatorattestationresponse">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'AuthenticatorAttestationResponse interface' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AuthenticatorAttestationResponse`

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

10.0

`attestationObject`

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

10.0

`getAuthenticatorData`

85

85

No

No

No

No

No

85

No

No

No

No

`getPublicKey`

85

85

No

No

No

No

No

85

No

No

No

No

`getPublicKeyAlgorithm`

85

85

No

No

No

No

No

85

No

No

No

No

`getTransports`

74

79

No

No

No

No

No

74

No

No

No

11.0

## See also

- [`AuthenticatorAssertionResponse`](authenticatorassertionresponse): the interface for the type of response given when retrieving an existing credential
- [`AuthenticatorResponse`](authenticatorresponse): the parent interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAttestationResponse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAttestationResponse</a>

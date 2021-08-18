# AuthenticatorResponse

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `AuthenticatorResponse` interface of the [Web Authentication API](web_authentication_api) is the base interface for interfaces that provide a cryptographic root of trust for a key pair. The child interfaces include information from the browser such as the challenge origin and either may be returned from [`PublicKeyCredential.response`](publickeycredential/response).

## Interfaces based on AuthenticatorResponse

Below is a list of interfaces based on the AuthenticatorResponse interface.

- [`AuthenticatorAssertionResponse`](authenticatorassertionresponse)
- [`AuthenticatorAttestationResponse`](authenticatorattestationresponse)

## Properties

[`AuthenticatorResponse.clientDataJSON`](authenticatorresponse/clientdatajson)  
A [JSON](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON) string in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), representing the client data that was passed to [`CredentialsContainer.create()`](credentialscontainer/create) or [`CredentialsContainer.get()`](credentialscontainer/get).

## Methods

None.

## Examples

### Getting an AuthenticatorAssertionResponse

    var options = {
      challenge: new Uint8Array([/* bytes sent from the server */])
    };

    navigator.credentials.get({ "publicKey": options })
        .then(function (credentialInfoAssertion) {
        var assertionResponse = credentialInfoAssertion.response;
        // send assertion response back to the server
        // to proceed with the control of the credential
    }).catch(function (err) {
         console.error(err);
    });

### Getting an AuthenticatorAttestationResponse

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
        var attestationResponse = newCredentialInfo.response;
      }).catch(function (err) {
         console.error(err);
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#authenticatorresponse">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'AuthenticatorResponse interface' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AuthenticatorResponse`

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

`clientDataJSON`

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

- [`AuthenticatorAttestationResponse`](authenticatorattestationresponse)
- [`AuthenticatorAssertionResponse`](authenticatorassertionresponse)
- [`PublicKeyCredential.response`](publickeycredential/response)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorResponse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorResponse</a>

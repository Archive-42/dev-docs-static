# PublicKeyCredentialRequestOptions.challenge

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `challenge` property of the [`PublicKeyCredentialRequestOptions`](../publickeycredentialrequestoptions) dictionary is a [`BufferSource`](../buffersource) used as [a cryptographic challenge](https://en.wikipedia.org/wiki/Challenge%E2%80%93response_authentication). This is randomly generated then sent from the relying party's server. This value (among other client data) will be signed by the authenticator's private key and produce [`AuthenticatorAssertionResponse.signature`](../authenticatorassertionresponse/signature) which should be sent back to the server as part of the response.

**Note:** When the credential is created with a [`navigator.credentials.create()`](../credentialscontainer/create) call, the signature of the challenge is contained within [`AuthenticatorAttestationResponse.attestationObject`](../authenticatorattestationresponse/attestationobject).

**Note:** A challenge will be at least 16 bytes long.

## Syntax

    challenge = publicKeyCredentialRequestOptions.challenge

### Value

A [`BufferSource`](../buffersource) which is at least 16 bytes long. Contains a cryptographic challenge emitted from the relying party's server which must be signed by the authenticator's private key and sent back (within the [response](../authenticatorassertionresponse/signature)) to the relying party's server for verification.

## Examples

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialrequestoptions-challenge">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'challenge' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`challenge`

67

≤79

60

No

54

13

67

67

?

48

13

No

## See also

- [`AuthenticatorAssertionResponse.signature`](../authenticatorassertionresponse/signature) which is produced using the challenge and the private key of the authenticator when fetching a credential.
- [`PublicKeyCredentialCreationOptions.challenge`](../publickeycredentialcreationoptions/challenge), the analogous option property used when creating a credential.
- [`AuthenticatorAttestationResponse.attestationObject`](../authenticatorattestationresponse/attestationobject) which contains the signature of the challenge within its `attStmt` property when creating a credential.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/challenge" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/challenge</a>

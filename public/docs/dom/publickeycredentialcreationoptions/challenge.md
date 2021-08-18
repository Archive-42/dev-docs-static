PublicKeyCredentialCreationOptions.challenge
============================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `challenge` property of the [`PublicKeyCredentialCreationOptions`](../publickeycredentialcreationoptions) dictionary is a [`BufferSource`](../buffersource) used as [a cryptographic challenge](https://en.wikipedia.org/wiki/Challenge%E2%80%93response_authentication). This is randomly generated then sent from the relying party's server. This value (among other client data) will be signed by the authenticator, using its private key, and must be sent back for verification to the server as part of [`AuthenticatorAttestationResponse.attestationObject`](../authenticatorattestationresponse/attestationobject).

**Note:** When the credential is retrieved with a [`navigator.credentials.get()`](../credentialscontainer/get) call, the signature of the challenge is contained in [`AuthenticatorAssertionResponse.signature`](../authenticatorassertionresponse/signature).

**Note:** A challenge will be at least 16 bytes long.

Syntax
------

    challenge = publicKeyCredentialCreationOptions.challenge

### Value

A [`BufferSource`](../buffersource) which is at least 16 bytes long. Contains a cryptographic challenge emitted from the relying party's server which must be signed by the authenticator's private key and sent back (within the [response](../authenticatorattestationresponse/attestationobject)) to the relying party's server for verification.

Examples
--------

    var publicKey = {
      challenge: new Uint8Array(26) /* this actually is given from the server */,
      rp: {
        name: "Example CORP",
        id  : "login.example.com"
      },
      user: {
        id: new Uint8Array(26), /* To be changed for each user */
        name: "jdoe@example.com",
        displayName: "John Doe",
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
        // send attestation response and client extensions
        // to the server to proceed with the registration
        // of the credential
      }).catch(function (err) {
         console.error(err);
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialcreationoptions-challenge">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'challenge' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`challenge`

67

≤79

60

No

54

13

No

67

?

48

13

No

See also
--------

-   [`AuthenticatorAttestationResponse.attestationObject`](../authenticatorattestationresponse/attestationobject) which contains the signature of the challenge within its `attStmt` property.
-   [`PublicKeyCredentialRequestOptions.challenge`](../publickeycredentialrequestoptions/challenge), the analogous option property used when fetching a credential.
-   [`AuthenticatorAssertionResponse.signature`](../authenticatorassertionresponse/signature) which is produced using the challenge and the private key of the authenticator when fetching a credential.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/challenge" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/challenge</a>

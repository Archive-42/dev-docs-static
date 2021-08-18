# AuthenticatorAttestationResponse.attestationObject

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `attestationObject` property of the [`AuthenticatorAttestationResponse`](../authenticatorattestationresponse) interface returns an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the new public key, as well as signature over the entire `attestationObject` with a private key that is stored in the authenticator when it is manufactured.

As part of the [`CredentialsContainer.create()`](../credentialscontainer/create) call, an authenticator will create a new keypair as well as an attestationObject for that keypair. The public key that corresponds to the private key that has created the attestation signature is well known; however, there are various well known attestation public key chains for different ecosystems (for example, Android or TPM attestations).

## Syntax

    attestObj = authenticatorAttestationResponse.attestationObject

## Properties

After decoding the [CBOR](https://datatracker.ietf.org/doc/html/rfc7049) encoded `ArrayBuffer`, the resulting JavaScript object will contain the following properties:

`authData`  
The same as [`AuthenticatorAssertionResponse.authenticatorData`](../authenticatorassertionresponse/authenticatordata). Note that in [`AuthenticatorAssertionResponse`](../authenticatorassertionresponse), the `authenticatorData` is exposed as a property in a JavaScript object while in [`AuthenticatorAttestationResponse`](../authenticatorattestationresponse), the `authenticatorData` is a property in a [CBOR](https://datatracker.ietf.org/doc/html/rfc7049) map.

The same [`AuthenticatorAssertionResponse.authenticatorData`](../authenticatorassertionresponse/authenticatordata) field is used by both `AuthenticatorAttestationResponse` and by `AuthenticatorAssertionResponse`. When used in attestation, it contains an optional field, `attestedCredentialData`. This field is not included when used in the `AuthenticatorAssertionResponse`. The attestedCredentialData field contains the `credentialId` and `credentialPublicKey`.

`fmt`  
A text string that indicates the format of the attStmt. The [WebAuthn specification defines a number of formats](https://www.w3.org/TR/webauthn/#defined-attestation-formats); however, formats may also be defined in other specifications and registered in an [IANA registry](https://www.w3.org/TR/webauthn/#sctn-att-fmt-reg). Formats defined by WebAuthn are:

- `"packed"`
- `"tpm"`
- `"android-key"`
- `"android-safetynet"`
- `"fido-u2f"`
- `"none"`

`attStmt`  
A an attestation statement that is of the format defined by `"fmt"`. For now, [see the WebAuthn specification for details on each format](https://www.w3.org/TR/webauthn/#defined-attestation-formats).

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
        var attestationObj = newCredentialInfo.response.attestationObject;
        // This will be a CBOR encoded ArrayBuffer

        // Do something with the response
        // (sending it back to the relying party server maybe?)
      }).catch(function (err) {
         console.error(err);
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-authenticatorattestationresponse-attestationobject">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'attestationObject' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [`PublicKeyCredentialCreationOptions.challenge`](../publickeycredentialcreationoptions/challenge): the cryptographic challenge which signature by the authenticator is contained in `attStmt`
- [`PublicKeyCredentialCreationOptions.attestation`](../publickeycredentialcreationoptions/attestation): the attestation statement transport option specified for the creation

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAttestationResponse/attestationObject" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAttestationResponse/attestationObject</a>

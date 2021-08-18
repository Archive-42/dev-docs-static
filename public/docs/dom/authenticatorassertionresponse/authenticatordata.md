# AuthenticatorAssertionResponse.authenticatorData

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `authenticatorData` property of the [`AuthenticatorAssertionResponse`](../authenticatorassertionresponse) interface returns an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing information from the authenticator such as the Relying Party ID Hash (rpIdHash), a signature counter, test of user presence, user verification flags, and any extensions processed by the authenticator.

## Syntax

    var authnrData = authenticatorAssertionResponse.authenticatorData;

### Value

An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) that has a [`ArrayBuffer.byteLength`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/byteLength) of at least 37 bytes, containing the following fields:

- **rpIdHash** (32 bytes) - A SHA256 hash of the [relying party ID](../publickeycredentialrequestoptions/rpid) that was seen by the browser. The server will ensure that this hash matches a hash of its own origin in order to prevent phishing or other man-in-the-middle attacks.
- **flags** (1 bytes) - A bitfield that indicates various attributes that were asserted by the authenticator. The bits are as follows, where "bit 0" is the least significant bit and all bits not specifically mentioned below are "reserved for future use":
  - Bit 0, User Presence (UP) - If set, authenticator validated that the user was present through some Test of User Presence (TUP), such as touching a button on the authenticator.
  - Bit 2, User Verification (UV) - If set, authenticator verified the actual user, through a biometric, PIN, or other authentication method.
  - Bit 6, Attested Credential Data (AT) - If set, attestedCredentialData will immediately follow the first 37 bytes of this authenticatorData.
  - Bit 7, Extension data (ED) - If set, extension data is present. Extension data will follow attestedCredentialData if it is present, or will immediately follow the first 37 bytes of the authenticatorData if no attestedCredentialData is present.
- **signCount** (4 bytes) - A signature count from the authenticator. The server will use this counter to detect authenticator cloning.
- **attestedCredentialData** (variable length) - The credential that was created. This is only present during a navigator.credentials.create() call. This is a sequence of bytes with the following format:
  - **AAGUID** (16 bytes) - Authenticator Attestation Globally Unique Identifier, a unique number that identifies the model of the authenticator (not the specific instance of the authenticator) so that a relying party can understand the characteristics of the authenticator by looking up its metadata statement.
  - **credentialIdLength** (2 bytes) - The length of the credential ID that immediately follows these bytes.
  - **credentialId** (variable length) - A unique identifier for this credential so that it can be requested for future authentications. The credential is "credentialIdLength" bytes long.
  - **credentialPublicKey** (variable length) - A [COSE](https://datatracker.ietf.org/doc/html/rfc8152) encoded public key. This public key will be stored on the server associated with a user's account and be used for future authentications.
- **extensions** (variable length) - An optional [CBOR](https://developer.mozilla.org/en-US/docs/Web) map of extensions.

## Examples

    var options = {
      challenge: new Uint8Array(26), // will be another value, provided by the relying party server
      timeout: 60000
    };

    navigator.credentials.get({  publickey: options })
      .then(function (assertionPKCred) {
        var authenticatorData = assertionPKCred.response.authenticatorData;
        // Maybe try to convert the authenticatorData to see what's inside

        // Send response and client extensions to the server so that it can
        // go on with the authentication

    }).catch(function (err) {
       console.error(err);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-authenticatorassertionresponse-authenticatordata">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'authenticatorData' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`authenticatorData`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAssertionResponse/authenticatorData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAssertionResponse/authenticatorData</a>

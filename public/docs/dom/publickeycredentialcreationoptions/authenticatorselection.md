PublicKeyCredentialCreationOptions.authenticatorSelection
=========================================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`authenticatorSelection`, an optional property of the [`PublicKeyCredentialCreationOptions`](../publickeycredentialcreationoptions) dictionary, is an object giving criteria to filter out the authenticators to be used for the creation operation.

Syntax
------

    authenticatorSelection = publicKeyCredentialCreationOptions.authenticatorSelection

### Value

An object with the following properties:

 `authenticatorAttachment`<span class="badge inline optional">Optional</span>   
A string which is either "`platform`" or "`cross-platform`". The former describes an authenticator which is bound to the client and which is generally not removable. The latter describes a device which may be used across different platform (such as a USB or NFC device).

 `requireResidentKey`<span class="badge inline optional">Optional</span>   
A boolean which indicated that the credential private key must be stored in the authenticator, the client or in a client device. The default value is `false`.

 `userVerification`<span class="badge inline optional">Optional</span>   
A string qualifying how the user verification should be part of the authentication process. The values may be:

-   "`required`": user verification is required, the operation will fail if the [response](../authenticatorattestationresponse) does not have the UV flag (as part of the `authenticatorData` property of [`AuthenticatorAttestationResponse.attestationObject`](../authenticatorattestationresponse/attestationobject))
-   "`preferred`": user verification is preferred, the operation will not fail if the [response](../authenticatorattestationresponse) does not have the UV flag (as part of the `authenticatorData` property of [`AuthenticatorAttestationResponse.attestationObject`](../authenticatorattestationresponse/attestationobject))
-   "`discouraged`": user verification should not be employed as to minimize the user interaction during the process.

The default value is "`preferred`".

The authenticator used for the creation of the public key credential must comply with the requirements.

**Note:** See [`PublicKeyCredential.isUserVerifyingPlatformAuthenticatorAvailable()`](../publickeycredential/isuserverifyingplatformauthenticatoravailable) which resolves to `true` when a user-verifiying platform authenticator is available.

Examples
--------

    var publicKey = {
      authenticatorSelection:{
        authenticatorAttachment: "cross-platform",
        requireResidentKey: true,
        userVerification: "required"
      },
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
      pubKeyCredParams: [ {
        type: "public-key",
        alg: -7 } ]
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialcreationoptions-authenticatorselection">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'authenticatorSelection' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`authenticatorSelection`

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

-   [`PublicKeyCredential.isUserVerifyingPlatformAuthenticatorAvailable()`](../publickeycredential/isuserverifyingplatformauthenticatoravailable)
-   [`AuthenticatorAssertionResponse.authenticatorData`](../authenticatorassertionresponse/authenticatordata) whose structure contains the UV flag (please note that for the creation operation, [`AuthenticatorAttestationResponse.attestationObject`](../authenticatorattestationresponse/attestationobject) only contains a CBOR encoded version of this data and does not give an immediate access to the flag).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/authenticatorSelection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/authenticatorSelection</a>

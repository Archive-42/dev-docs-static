# PublicKeyCredentialCreationOptions

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PublicKeyCredentialCreationOptions` dictionary of the [Web Authentication API](web_authentication_api) holds options passed to [`navigators.credentials.create()`](credentialscontainer/create) in order to create a [`PublicKeyCredential`](publickeycredential).

## Properties

[`PublicKeyCredentialCreationOptions.rp`](publickeycredentialcreationoptions/rp)  
An object describing the relying party which requested the credential creation.

[`PublicKeyCredentialCreationOptions.user`](publickeycredentialcreationoptions/user)  
An object describing the user account for which the credential is generated.

[`PublicKeyCredentialCreationOptions.challenge`](publickeycredentialcreationoptions/challenge)  
A [`BufferSource`](buffersource), emitted by the relying party's server and used as a [cryptographic challenge](https://en.wikipedia.org/wiki/Challenge%E2%80%93response_authentication). This value will be signed by the authenticator and the signature will be sent back as part of [`AuthenticatorAttestationResponse.attestationObject`](authenticatorattestationresponse/attestationobject).

[`PublicKeyCredentialCreationOptions.pubKeyCredParams`](publickeycredentialcreationoptions/pubkeycredparams)  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of element which specify the desired features of the credential, including its type and the algorithm used for the cryptographic signature operations. This array is sorted by descending order of preference.

[`PublicKeyCredentialCreationOptions.timeout`](publickeycredentialcreationoptions/timeout) <span class="badge inline optional">Optional</span>  
A numerical hint, in milliseconds, which indicates the time the caller is willing to wait for the creation operation to complete. This hint may be overridden by the browser.

[`PublicKeyCredentialCreationOptions.excludeCredentials`](publickeycredentialcreationoptions/excludecredentials) <span class="badge inline optional">Optional</span>  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of descriptors for existing credentials. This is provided by the relying party to avoid creating new public key credentials for an existing user who already have some.

[`PublicKeyCredentialCreationOptions.authenticatorSelection`](publickeycredentialcreationoptions/authenticatorselection) <span class="badge inline optional">Optional</span>  
An object whose properties are criteria used to filter out the potential authenticators for the creation operation.

[`PublicKeyCredentialCreationOptions.attestation`](publickeycredentialcreationoptions/attestation) <span class="badge inline optional">Optional</span>  
A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) which indicates how the attestation (for the authenticator's origin) should be transported.

[`PublicKeyCredentialCreationOptions.extensions`](publickeycredentialcreationoptions/extensions) <span class="badge inline optional">Optional</span>  
An object with several client extensions' inputs. Those extensions are used to request additional processing (e.g. dealing with legacy FIDO APIs credentials, prompting a specific text on the authenticator, etc.).

## Methods

None.

## Examples

    // some examples of COSE algorithms
    const cose_alg_ECDSA_w_SHA256 = -7;
    const cose_alg_ECDSA_w_SHA512 = -36;

    var createCredentialOptions = {
        // Format of new credentials is publicKey
        publicKey: {
            // Relying Party
            rp: {
                name: "Example CORP",
                id: "login.example.com",
                icon: "https://login.example.com/login.ico"
            },
            // Cryptographic challenge from the server
            challenge: new Uint8Array(26),
            // User
            user: {
                id: new Uint8Array(16),
                name: "john.p.smith@example.com",
                displayName: "John P. Smith",
            },
            // Requested format of new keypair
            pubKeyCredParams: [{
                type: "public-key",
                alg: cose_alg_ECDSA_w_SHA256,
            }],
            // Timeout after 1 minute
            timeout: 60000,
            // Do not send the authenticator's origin attestation
            attestation: "none",
            extensions: {
              uvm: true,
              exts: true
            },
            // Filter out authenticators which are bound to the device
            authenticatorSelection:{
              authenticatorAttachment: "cross-platform",
              requireResidentKey: true,
              userVerification: "preferred"
            },
            // Exclude already existing credentials for the user
            excludeCredentials: [
              {
                type: "public-key",
                // the id for john.doe@example.com
                id  : new Uint8Array(26) /* this actually is given by the server */
              },
              {
                type: "public-key",
                // the id for john-doe@example.com
                id : new Uint8Array(26) /* another id */
              }
            ]
        }
    };

    // Create the new credential with the options above
    navigator.credentials.create(createCredentialOptions)
      .then(function (newCredentialInfo) {
        var attestationResponse = newCredentialInfo.response;
        var clientExtensionsOutputs = newCredentialInfo.getClientExtensionsResults();

        // Send the response to the relying party server
        // it will verify the content and integrity before
        // creating a new credential

      }).catch(function (err) {
        // Deal with any error properly
        console.error(err);
      });;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dictdef-publickeycredentialcreationoptions">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'PublicKeyCredentialCreationOptions dictionary' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PublicKeyCredentialCreationOptions`

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

`attestation`

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

`excludeCredentials`

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

`extensions`

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

`pubKeyCredParams`

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

`rp`

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

`timeout`

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

`user`

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

## See also

- <span class="page-not-created">`PublicKeyRequestOptions`</span>: the dictionary which provides option for the public key retrieval operation

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions</a>

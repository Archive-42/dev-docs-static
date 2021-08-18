# PublicKeyCredentialRequestOptions.userVerification

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`userVerification` is an optional property of the [`PublicKeyCredentialRequestOptions`](../publickeycredentialrequestoptions). This is a string which indicates how the user verification should be part of the authentication process.

**Note:** An analogous option exists for the creation operation ([`navigators.credentials.create()`](../credentialscontainer/create)), see the `userVerification` property of [`PublicKeyCredentialCreationOptions.authenticatorSelection`](../publickeycredentialcreationoptions/authenticatorselection).

## Syntax

    userVerification = publicKeyCredentialRequestOptions.userVerification

### Value

A string qualifying how the user verification should be part of the authentication process. The values may be:

- `"required"`: user verification is required, the operation will fail if the [response](../authenticatorassertionresponse) does not have the UV flag (as part of [`AuthenticatorAssertionResponse.authenticatorData`](../authenticatorassertionresponse/authenticatordata))
- `"preferred"`: user verification is preferred, the operation will not fail if the [response](../authenticatorassertionresponse) does not have the UV flag (as part of [`AuthenticatorAssertionResponse.authenticatorData`](../authenticatorassertionresponse/authenticatordata))
- `"discouraged"`: user verification should not be employed as to minimize the user interaction during the process.

The default value is `"preferred"`.

## Examples

    var options = {
      userVerification: "preferred",
      challenge: new Uint8Array([/* bytes sent from the server */]),
    };

    navigator.credentials.get({ "publicKey": options })
        .then(function (credentialInfoAssertion) {
        // send assertion response back to the server
        // to proceed with the control of the credential
    }).catch(function (err) {
         console.error(err);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialrequestoptions-userverification">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'userVerification' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`userVerification`

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

- [`PublicKeyCredentialCreationOptions.authenticatorSelection`](../publickeycredentialcreationoptions/authenticatorselection) whose `userVerification` property serves the same purpose for credential creation.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/userVerification" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/userVerification</a>

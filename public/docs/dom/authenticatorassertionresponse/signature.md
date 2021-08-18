# AuthenticatorAssertionResponse.signature

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `signature` read-only property of the [`AuthenticatorAssertionResponse`](../authenticatorassertionresponse) interface is an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) object which is the signature of the authenticator for both [`AuthenticatorAssertionResponse.authenticatorData`](authenticatordata) and a SHA-256 hash of the client data ([`AuthenticatorAssertionResponse.clientDataJSON`](../authenticatorresponse/clientdatajson)).

This signature will be sent to the server for control, as part of the response. It provides the proof that an authenticator does possess the private key which was used for the credential's generation.

**Note:** An `AuthenticatorAssertionResponse` instance is available on [`PublicKeyCredential.response`](../publickeycredential/response) after calling [`navigator.credentials.get()`](../credentialscontainer/get).

**Note:** This property may only be used in top-level contexts and will not be available in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) for example.

## Syntax

    signature = authenticatorAssertionResponse.signature

### Value

An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) object which the signature of the authenticator (using its private key) for both [`AuthenticatorAssertionResponse.authenticatorData`](authenticatordata) and a SHA-256 hash given by the client for its data (the challenge, the origin, etc. and available from [`AuthenticatorAssertionResponse.clientDataJSON`](../authenticatorresponse/clientdatajson)).

## Examples

    var options = {
      challenge: new Uint8Array(26), // will be another value, provided by the relying party server
      timeout: 60000
    };

    navigator.credentials.get({  publickey: options })
      .then(function (assertionPKCred) {
        var signature = assertionPKCred.response.signature;

        // Send response and client extensions to the server so that it can
        // go on with the authentication

    }).catch(function (err) {
       console.error(err);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-authenticatorassertionresponse-signature">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'signature' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`signature`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAssertionResponse/signature" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAssertionResponse/signature</a>

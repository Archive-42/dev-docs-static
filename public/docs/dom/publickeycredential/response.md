# PublicKeyCredential.response

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `response` read-only property of the [`PublicKeyCredential`](../publickeycredential) interface is an [`AuthenticatorResponse`](../authenticatorresponse) object which is sent from the authenticator to the user agent for the creation/fetching of credentials. The information contained in this response will be used by the relying party's server to verify the demand is legitimate.

An `AuthenticatorResponse` is either:

- an [`AuthenticatorAttestationResponse`](../authenticatorattestationresponse) (when the `PublicKeyCredential` is created via [`CredentialsContainer.create()`](../credentialscontainer/create))
- an [`AuthenticatorAssertionResponse`](../authenticatorassertionresponse) (when the `PublicKeyCredential` is obtained via [`CredentialsContainer.get()`](../credentialscontainer/get)).

In order to validate the _creation_ of credentials, a relying party's server needs both:

- this response
- the extensions of the client (given by [`PublicKeyCredential.getClientExtensionResults()`](getclientextensionresults)) to validate the demand.

**Note:** When validating the fetching of existing credentials, the whole `PublicKeyCredential` object and the client extensions are necessary for the relying party's server.

**Note:** This property may only be used in top-level contexts and will not be available in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) for example.

## Syntax

    response = publicKeyCredential.response

### Value

An [`AuthenticatorResponse`](../authenticatorresponse) object containing the data a relying party's script will receive and which should be sent to the relying party's server in order to validate the demand for creation or fetching. This object contains data from the client ([`AuthenticatorResponse/clientDataJSON`](../authenticatorresponse/clientdatajson)) and from the authenticator.

## Examples

    var options = {
      challenge: new Uint8Array(16) /* from the server */,
      rp: {
        name: "Example CORP",
        id  : "login.example.com"
      },
      user: {
        id: new Uint8Array(16) /* from the server */,
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

    navigator.credentials.create({  publickey: options })
      .then(function (pubKeyCredential) {
        var response = pubKeyCredential.response;
        var clientExtResults = pubKeyCredential.getClientExtensionResults();
        // Send response and client extensions to the server so that it can validate
        // and create credentials

    }).catch(function (err) {
      // Deal with any error
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredential-response">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'response' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`response`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/response" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/response</a>

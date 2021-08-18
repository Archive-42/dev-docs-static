# AuthenticatorAssertionResponse

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `AuthenticatorAssertionResponse` interface of the [Web Authentication API](web_authentication_api) is returned by [`CredentialsContainer.get()`](credentialscontainer/get) when a [`PublicKeyCredential`](publickeycredential) is passed, and provides proof to a service that it has a key pair and that the authentication request is valid and approved.

This interface inherites from [`AuthenticatorResponse`](authenticatorresponse).

**Note:** This interface is restricted to top-level contexts. Use from within an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) element will not have any effect.

## Properties

`AuthenticatorAssertionResponse.clientDataJSON` <span class="notecard inline secure">Secure context</span><span class="badge inline readonly">Read only </span>  
The client data for the authentication, such as origin and challenge. The <span class="page-not-created">`clientDataJSON`</span> property is inherited from the [`AuthenticatorResponse`](authenticatorresponse).

[`AuthenticatorAssertionResponse.authenticatorData`](authenticatorassertionresponse/authenticatordata) <span class="notecard inline secure">Secure context</span><span class="badge inline readonly">Read only </span>  
An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing information from the authenticator such as the Relying Party ID Hash (rpIdHash), a signature counter, test of user presence and user verification flags, and any extensions processed by the authenticator.

[`AuthenticatorAssertionResponse.signature`](authenticatorassertionresponse/signature) <span class="notecard inline secure">Secure context</span><span class="badge inline readonly">Read only </span>  
An assertion signature over [`AuthenticatorAssertionResponse.authenticatorData`](authenticatorassertionresponse/authenticatordata) and [`AuthenticatorResponse.clientDataJSON`](authenticatorresponse/clientdatajson). The assertion signature is created with the private key of keypair that was created during the [`navigator.credentials.create()`](credentialscontainer/create) call and verified using the public key of that same keypair.

[`AuthenticatorAssertionResponse.userHandle`](authenticatorassertionresponse/userhandle) <span class="notecard inline secure">Secure context</span><span class="badge inline readonly">Read only </span>  
An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing an opaque user identifier.

## Methods

None.

## Examples

    var options = {
      challenge: new Uint8Array([/* bytes sent from the server */])
    };

    navigator.credentials.get({ "publicKey": options })
        .then(function (credentialInfoAssertion) {
        var assertionResponse = credentialInfoAssertion.response;
        // Do something specific with the response

        // send assertion response back to the server
        // to proceed with the control of the credential
    }).catch(function (err) {
         console.error(err);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#iface-authenticatorassertionresponse">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'AuthenticatorAssertionResponse interface' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AuthenticatorAssertionResponse`

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

`userHandle`

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

- [`AuthenticatorAttestationResponse`](authenticatorattestationresponse): the interface for the type of response given when creating a new credential
- [`AuthenticatorResponse`](authenticatorresponse): the parent interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAssertionResponse" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAssertionResponse</a>

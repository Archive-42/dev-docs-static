# AuthenticatorResponse.clientDataJSON

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `clientDataJSON` property of the [`AuthenticatorResponse`](../authenticatorresponse) interface stores a [JSON](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON) string in an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), representing the client data that was passed to [`CredentialsContainer.create()`](../credentialscontainer/create) or [`CredentialsContainer.get()`](../credentialscontainer/get). This property is only accessed on one of the child objects of `AuthenticatorResponse`, specifically [`AuthenticatorAttestationResponse`](../authenticatorattestationresponse) or [`AuthenticatorAssertionResponse`](../authenticatorassertionresponse).

## Syntax

    var arrayBuffer = AuthenticatorAttestationResponse.clientDataJSON;
    var arrayBuffer = AuthenticatorAssertionResponse.clientDataJSON;

### Value

An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

## Properties

After the `clientDataJSON` object is converted from an `ArrayBuffer` to a JavaScript object, it will have the following properties:

`type`  
A string which is either `"webauthn.get"` when an existing credential is retrieved or `"webauthn.create"` when a new credential is created.

`challenge`  
The [base64url](https://developer.mozilla.org/en-US/docs/Glossary/Base64) encoded version of the cryptographic challenge sent from the relying party's server. The original value is passed via [`PublicKeyCredentialRequestOptions.challenge`](../publickeycredentialrequestoptions/challenge) or [`PublicKeyCredentialCreationOptions.challenge`](../publickeycredentialcreationoptions/challenge).

`origin`  
The fully qualified origin of the requester which has been given by the client/browser to the authenticator. We should expect the [relying party's id](../publickeycredentialrequestoptions/rpid) to be a suffix of this value.

`tokenBindingId` <span class="badge inline optional">Optional</span>  
An object describing the state of [the token binding protocol](https://datatracker.ietf.org/doc/html/rfc8471) for the communication with the relying party. It has two properties:

- `status`: A string which is either `"supported"` which indicates the client support token binding but did not negotiate with the relying party or `"present"` when token binding was used already
- `id`: A [`DOMString`](../domstring) which is the [base64url](https://developer.mozilla.org/en-US/docs/Glossary/Base64) encoding of the token binding ID which was used for the communication.

Should this property be absent, it would indicate that the client does not support token binding.

## Examples

    function arrayBufferToStr(buf) {
        return String.fromCharCode.apply(null, new Uint8Array(buf));
    }

    // pk is a PublicKeyCredential that is the result of a create() or get() Promise
    var clientDataStr = arrayBufferToStr(pk.clientDataJSON);
    var clientDataObj = JSON.parse(clientDataStr);

    console.log(clientDataObj.type);      // "webauthn.create" or "webauthn.get"
    console.log(clientDataObj.challenge); // base64 encoded String containing the original challenge
    console.log(clientDataObj.origin);    // the window.origin

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-authenticatorresponse-clientdatajson">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'clientDataJSON' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`clientDataJSON`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorResponse/clientDataJSON" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorResponse/clientDataJSON</a>

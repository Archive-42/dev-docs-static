# AuthenticatorAssertionResponse.userHandle

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `userHandle` read-only property of the [`AuthenticatorAssertionResponse`](../authenticatorassertionresponse) interface is an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) object which is an opaque identifier for the given user. Such an identifier can be used by the relying party's server to link the user account with its corresponding credentials and other data.

The same value may be found on the `id` property of the [`options.user`](../publickeycredentialcreationoptions/user) object (used for the creation of the `PublicKeyCredential` instance).

**Note:** An `AuthenticatorAssertionResponse` instance is available on [`PublicKeyCredential.response`](../publickeycredential/response) after calling [`navigator.credentials.get()`](../credentialscontainer/get).

**Note:** This property may only be used in top-level contexts and will not be available in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) for example.

## Syntax

    userHandle = authenticatorAssertionResponse.userHandle

### Value

An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) object which is an opaque identifier for the current user. This is not human-readable and does **not** contain any personally identifying information (e.g. username, e-mail, phone number, etc.)

## Examples

    var options = {
      challenge: new Uint8Array(26), // will be another value, provided by the relying party server
      timeout: 60000
    };

    navigator.credentials.get({  publickey: options })
      .then(function (assertionPKCred) {
        var userHandle = assertionPKCred.response.userHandle;

        // Send response and client extensions to the server so that it can
        // go on with the authentication

    }).catch(function (err) {
       console.error(err);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-authenticatorassertionresponse-userhandle">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'userHandle' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

- [`PublicKeyCredentialCreationOptions.user`](../publickeycredentialcreationoptions/user) and its `id` property which contains the same data

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAssertionResponse/userHandle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAssertionResponse/userHandle</a>

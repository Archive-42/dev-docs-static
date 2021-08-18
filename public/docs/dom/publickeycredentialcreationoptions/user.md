# PublicKeyCredentialCreationOptions.user

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `user` property of the [`PublicKeyCredentialCreationOptions`](../publickeycredentialcreationoptions) dictionary is an object describing the user account for which the credentials are generated (via [`navigator.credentials.create()`](../credentialscontainer/create)).

## Syntax

    userAccount = publicKeyCredentialCreationOptions.user

## Properties

`displayName`  
A [`DOMString`](../domstring) which is human readable and intended for display. It may be the full name of the user (e.g. `"John Doe"`). This is not intended to store the login of the user (see `name` below).

`icon` <span class="badge inline optional">Optional</span>  
An URL as a [`USVString`](../usvstring) value which points to an image resource which can be the avatar image for the user.

`id`  
A [`BufferSource`](../buffersource) uniquely identifying a given user. This an opaque identifier which can be used by the authenticator to link the user account with its corresponding credentials. This value will later be used when fetching the credentials in [`AuthenticatorAssertionResponse.userHandle`](../authenticatorassertionresponse/userhandle).

`name`  
A [`DOMString`](../domstring) giving a human-readable name for the user's identifier (e.g. `"jdoe@example.com"`).This property is intended for display and may be use to distinguish different account with the same `displayName`.

## Examples

    var publicKey = {
      challenge: new Uint8Array(26) /* this actually is given from the server */,
      rp: {
        name: "Example CORP",
        id  : "login.example.com"
      },
      user: {
        // To be changed for each user
        id: new Uint8Array.from(window.atob("LAEGMLKJNRLKGNAMLAFALFKA="), c=>c.charCodeAt(0));

        name: "jdoe@example.com",
        displayName: "John Doe",
        icon: "https://gravatar.com/avatar/jdoe.png"
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
        // send attestation response and client extensions
        // to the server to proceed with the registration
        // of the credential
      }).catch(function (err) {
         console.error(err);
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialcreationoptions-user">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'user' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

- [`AuthenticatorAssertionResponse.userHandle`](../authenticatorassertionresponse/userhandle) which should match the `id` property of `user` for the same user/credential.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/user" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/user</a>

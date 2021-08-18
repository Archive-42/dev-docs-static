PublicKeyCredentialRequestOptions
=================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PublicKeyCredentialRequestOptions` dictionary of the [Web Authentication API](web_authentication_api) holds the options passed to [`navigator.credentials.get()`](credentialscontainer/get) in order to fetch a given [`PublicKeyCredential`](publickeycredential).

Properties
----------

[`PublicKeyCredentialRequestOptions.challenge`](publickeycredentialrequestoptions/challenge)  
A [`BufferSource`](buffersource), emitted by the relying party's server and used as a [cryptographic challenge](https://en.wikipedia.org/wiki/Challenge%E2%80%93response_authentication). This value will be signed by the authenticator and the signature will be sent back as part of [`AuthenticatorAssertionResponse.signature`](authenticatorassertionresponse/signature).

 [`PublicKeyCredentialRequestOptions.timeout`](publickeycredentialrequestoptions/timeout) <span class="badge inline optional">Optional</span>   
A numerical hint, in milliseconds, which indicates the time the caller is willing to wait for the retrieval operation to complete. This hint may be overridden by the browser.

 [`PublicKeyCredentialRequestOptions.rpId`](publickeycredentialrequestoptions/rpid) <span class="badge inline optional">Optional</span>   
A [`USVString`](usvstring) which indicates the relying party's identifier (ex. `"login.example.org"`). If this option is not provided, the client will use the current origin's domain.

 [`PublicKeyCredentialRequestOptions.allowCredentials`](publickeycredentialrequestoptions/allowcredentials) <span class="badge inline optional">Optional</span>   
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of credentials descriptor which restricts the acceptable existing credentials for retrieval.

 [`PublicKeyCredentialRequestOptions.userVerification`](publickeycredentialrequestoptions/userverification) <span class="badge inline optional">Optional</span>   
A string qualifying how the user verification should be part of the authentication process.

 [`PublicKeyCredentialRequestOptions.extensions`](publickeycredentialrequestoptions/extensions) <span class="badge inline optional">Optional</span>   
An object with several client extensions' inputs. Those extensions are used to request additional processing (e.g. dealing with legacy FIDO APIs credentials, prompting a specific text on the authenticator, etc.).

Methods
-------

None.

Examples
--------

    var options = {
      challenge: new Uint8Array([/* bytes sent from the server */]),
      rpId: "example.com", /* will only work if the current domain
                             is something like foo.example.com */
      userVerification: "preferred",
      timeout: 60000,     // Wait for a minute
      allowCredentials: [
        {
          transports: "usb",
          type: "public-key",
          id: new Uint8Array(26) // actually provided by the server
        },
        {
          transports: "internal",
          type: "public-key",
          id: new Uint8Array(26) // actually provided by the server
        }
      ],
      extensions: {
        uvm: true,  // RP wants to know how the user was verified
        loc: false,
        txAuthSimple: "Could you please verify yourself?"
      }
    };

    navigator.credentials.get({ "publicKey": options })
        .then(function (credentialInfoAssertion) {
        // send assertion response back to the server
        // to proceed with the control of the credential
    }).catch(function (err) {
         console.error(err);
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dictdef-publickeycredentialrequestoptions">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'PublicKeyCredentialRequestOptions dictionary' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PublicKeyCredentialRequestOptions`

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

`allowCredentials`

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

`challenge`

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

`extensions`

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

`rpId`

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

`timeout`

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

See also
--------

-   [`PublicKeyCredentialCreationOptions`](publickeycredentialcreationoptions): the dictionary which provides option for the public key credential creation

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions</a>

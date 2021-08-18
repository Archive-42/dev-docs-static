PublicKeyCredentialRequestOptions.rpId
======================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `rpId` property, of the [`PublicKeyCredentialRequestOptions`](../publickeycredentialrequestoptions) dictionary, is an optional property which indicates the relying party's identifier as a [`USVString`](../usvstring). Its value can only be a suffix of the current origin's domain. For example, if you are browsing on `foo.example.com`, the `rpId` value may be `"example.com"` but not `"bar.org"` or `"baz.example.com"`.

This property is optional. If it is not explicitly provided, the user agent will use the value of the current origin's domain.

**Note:** An analogous option exists for the creation operation ([`navigators.credentials.create()`](../credentialscontainer/create)), see the `id` property of [`PublicKeyCredentialCreationOptions.rp`](../publickeycredentialcreationoptions/rp).

Syntax
------

    rpId = publicKeyCredentialRequestOptions.rpId

### Value

A [`USVString`](../usvstring) for the identifier of the relying party. Its value can only be a suffix of the current origin's domain.

Examples
--------

    var options = {
      challenge: new Uint8Array([/* bytes sent from the server */]),
      rpId: "example.com" // will only work if the current domain
                          // is something like foo.example.com
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialrequestoptions-rpid">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'rpId' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`PublicKeyCredentialCreationOptions.rp`](../publickeycredentialcreationoptions/rp) which represents the relying party (including its ID) for the creation operation

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/rpId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/rpId</a>

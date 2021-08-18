PublicKeyCredentialCreationOptions.rp
=====================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `rp` property of the [`PublicKeyCredentialCreationOptions`](../publickeycredentialcreationoptions) dictionary is an object describing the relying party which requested the credential creation (via [`navigator.credentials.create()`](../credentialscontainer/create)).

Syntax
------

    relyingPartyObj = publicKeyCredentialCreationOptions.rp

Properties
----------

 `icon` <span class="badge inline optional">Optional</span>   
An URL as a [`USVString`](../usvstring) value which points to an image resource which can be the logo/icon of the relying party.

`id`  
A [`DOMString`](../domstring) uniquely identifying a relying party. The default value of this property is the domain of the current document (e.g. `"login.example.com"`). It may be overridden with a suffix of the current domain (e.g. `"example.com"`).

`name`  
A [`DOMString`](../domstring) giving a human-readable name for the relying party. This property is intended for display (e.g. `"Example CORP"`).

Examples
--------

    var publicKey = {
      challenge: /* from the server */,
      rp: {
        name: "Example CORP",
        id  : "login.example.com",
        icon: "https://login.example.com/login.ico"
      },
      user: {
        id: new Uint8Array(16),
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

    navigator.credentials.create({ publicKey })
      .then(function (newCredentialInfo) {
        // send attestation response and client extensions
        // to the server to proceed with the registration
        // of the credential
      }).catch(function (err) {
         console.error(err);
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialcreationoptions-rp">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'rp' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/rp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/rp</a>

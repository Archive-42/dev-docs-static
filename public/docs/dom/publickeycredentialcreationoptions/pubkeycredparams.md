PublicKeyCredentialCreationOptions.pubKeyCredParams
===================================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `pubKeyCredParams` property of the [`PublicKeyCredentialCreationOptions`](../publickeycredentialcreationoptions) dictionary is an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) whose elements are objects describing the desired features of the credential to be created. These objects define the type of public-key and the algorithm used for [cryptographic signature](https://en.wikipedia.org/wiki/Digital_signature) operations.

If this array contains multiple elements, they are sorted by descending order of preference.

Syntax
------

    pubKeyCredParams = publicKeyCredentialCreationOptions.pubKeyCredParams

### Value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) whose elements are objects with the following properties:

`type`  
A string describing type of public-key credential to be created. As of this writing (March 2019), only `"public-key"` may be used.

`alg`  
A numeric identifier for the algorithm to be used to generate the key pair. The links between identifier and algorithms are defined in [this IANA registry](https://www.iana.org/assignments/cose/cose.xhtml#algorithms) (e.g. `-7` indicates the elliptic curve algorithm ECDSA with SHA-256).

Though those elements are sorted by preference (the first element being the most preferred), it is up to the client to choose among those elements for building the credential.

Examples
--------

    var publicKey = {
      pubKeyCredParams: [
        // We would like an elliptic curve to be used if possible
        {
          type: "public-key",
          alg: -7
        },
        // If not, then we will fallback on an RSA algorithm
        {
          type: "public-key",
          alg: -37
        }
      ],
      challenge: new Uint8Array(26) /* this actually is given from the server */,
      rp: {
        name: "Example CORP",
        id  : "login.example.com"
      },
      user: {
        id: new Uint8Array(26), /* To be changed for each user */
        name: "jdoe@example.com",
        displayName: "John Doe",
      }
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialcreationoptions-pubkeycredparams">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'pubKeyCredParams' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pubKeyCredParams`

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

See also
--------

-   [The IANA COSE Algorithms registry](https://www.iana.org/assignments/cose/cose.xhtml#algorithms) which describes the cryptographic algorithms and their corresponding identifier (used as the `"alg"` key here)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/pubKeyCredParams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/pubKeyCredParams</a>

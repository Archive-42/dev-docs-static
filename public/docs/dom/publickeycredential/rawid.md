PublicKeyCredential.rawId
=========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `rawId` read-only property of the [`PublicKeyCredential`](../publickeycredential) interface is an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) object containing the identifier of the credentials.

The [`PublicKeyCredential.id`](id) property is a [base64url encoded](https://developer.mozilla.org/en-US/docs/Glossary/Base64) version of this identifier.

**Note:** This property may only be used in top-level contexts and will not be available in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) for example.

Syntax
------

    rawId = publicKeyCredential.rawId

### Value

A [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the identifier of the credentials. This identifier is expected to be globally unique and is appointed for the current `PublicKeyCredential` and its associated [`AuthenticatorAssertionResponse`](../authenticatorassertionresponse).

Examples
--------

    var options = {
      challenge: new Uint8Array(26) /* from the server */,
      rp: {
        name: "Example CORP",
        id  : "login.example.com"
      },
      user: {
        id: new Uint8Array(26), /* To be changed for each user */
        name: "jdoe@example.com",
        displayName: "John Doe",
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
        var rawId = pubKeyCredential.rawId;
        // Do something with rawId
    }).catch(function (err) {
      // Deal with any error
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredential-rawid">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'rawId' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`rawId`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/rawId" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/rawId</a>

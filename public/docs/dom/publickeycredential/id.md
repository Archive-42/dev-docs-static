PublicKeyCredential.id
======================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `id` read-only property of the [`PublicKeyCredential`](../publickeycredential) interface is a [`DOMString`](../domstring), inherited from [`Credential`](../credential), which represents the identifier of the current `PublicKeyCredential` instance.

This property is a [base64url encoded](https://developer.mozilla.org/en-US/docs/Glossary/Base64) version of [`PublicKeyCredential.rawId`](rawid).

**Note:** This property may only be used in top-level contexts and will not be available in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) for example.

Syntax
------

    id = publicKeyCredential.id

### Value

A [`DOMString`](../domstring) being the [base64url encoded](https://developer.mozilla.org/en-US/docs/Glossary/Base64) version of [`PublicKeyCredential.rawId`](rawid).

Examples
--------

    var publicKey = {
      challenge: new Uint8Array(26) /* this actually is given from the server */,
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

    navigator.credentials.create({ publicKey })
      .then(function (newCredentialInfo) {
        var id = newCredentialInfo.id;
        // Do something with the id

        // send attestation response and client extensions
        // to the server to proceed with the registration
        // of the credential
      }).catch(function (err) {
         console.error(err);
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#iface-pkcredential">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'id' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Specified in the context of <code>PublicKeyCredential</code>. Overrides the getter defined in <code>Credential</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-credential-management/#dom-credential-id">Credential Management Level 1<br />
<span class="small">The definition of 'id' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.PublicKeyCredential.id`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [`Credential.id`](../credential/id)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/id</a>

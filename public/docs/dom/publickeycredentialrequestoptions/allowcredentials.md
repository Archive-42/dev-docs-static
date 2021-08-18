PublicKeyCredentialRequestOptions.allowCredentials
==================================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`allowCredentials` is an optional property of the [`PublicKeyCredentialRequestOptions`](../publickeycredentialrequestoptions) dictionary which indicates the existing credentials acceptable for retrieval. This is an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of credential descriptors.

**Note:** [`PublicKeyCredentialCreationOptions.excludeCredentials`](../publickeycredentialcreationoptions/excludecredentials) may be used during the creation of the credentials in order to avoid creating new credentials for an existing user with existing public key credential. Contrary to `allowCredentials`, it is used to *filter out* credentials.

Syntax
------

    allowCredentials = publicKeyCredentialRequestOptions.allowCredentials

### Value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) whose elements are objects with the following properties:

`type`  
A string describing type of public-key credential to be created. As of this writing (March 2019), only `"public-key"` may be used.

`id`  
A [`BufferSource`](../buffersource) matching an existing public key credential identifier ([`PublicKeyCredential.rawId`](../publickeycredential/rawid)). This identifier is generated during the creation of the `PublicKeyCredential` instance.

 `transports` <span class="badge inline optional">Optional</span>   
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of strings describing the possible transports between the client and the authenticator. The value of the strings may be:

-   `"usb"`: the authenticator can be contacted via a removable USB link
-   `"nfc"`: the authenticator may be used over [NFC (Near Field Communication)](https://en.wikipedia.org/wiki/Near-field_communication)
-   `"ble"`: the authenticator may be used over [BLE (Bluetooth Low Energy)](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy)
-   `"internal"`: the authenticator is specifically bound to the client device (cannot be removed).

If the authenticator does not contain any of these public key credentials, the client will throw a [`DOMException`](../domexception) `"NotAllowedError"`.

Examples
--------

    var options = {
      allowCredentials: [
        {
          transports: ["usb"],
          type: "public-key",
          id: new Uint8Array(26) // actually provided by the server
        },
        {
          transports: ["internal"],
          type: "public-key",
          id: new Uint8Array(26) // actually provided by the server
        }
      ],
      challenge: new Uint8Array([/* bytes sent from the server */])
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialrequestoptions-allowcredentials">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'allowCredentials' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`PublicKeyCredentialCreationOptions.excludeCredentials`](../publickeycredentialcreationoptions/excludecredentials) which is used to filter out existing credentials during creation and avoid creating new credentials for an existing user

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/allowCredentials" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/allowCredentials</a>

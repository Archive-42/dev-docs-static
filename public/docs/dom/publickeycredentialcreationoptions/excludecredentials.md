# PublicKeyCredentialCreationOptions.excludeCredentials

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`excludeCredentials`, an optional property of the [`PublicKeyCredentialCreationOptions`](../publickeycredentialcreationoptions) dictionary, is an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) whose elements are descriptors for the public keys already existing for a given user. This is provided by the relying party's server if it wants to prevent creation of new credentials for an existing user.

## Syntax

    excludeCredentials = publicKeyCredentialCreationOptions.excludeCredentials

### Value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) whose elements are objects with the following properties:

`type`  
A string describing type of public-key credential to be created. As of this writing (March 2019), only "`public-key`" may be used.

`id`  
A [`BufferSource`](../buffersource) matching an existing public key credential identifier ([`PublicKeyCredential.rawId`](../publickeycredential/rawid)). This identifier is generated during the creation of the `PublicKeyCredential` instance.

`transports` <span class="badge inline optional">Optional</span>  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of strings describing the possible transports between the client and the authenticator. The value of the strings may be:

- "`usb`": the authenticator can be contacted via a removable USB link
- "`nfc`": the authenticator may be used over [NFC (Near Field Communication)](https://en.wikipedia.org/wiki/Near-field_communication)
- "`ble`": the authenticator may be used over [BLE (Bluetooth Low Energy)](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy)
- "`internal`": the authenticator is specifically bound to the client device (cannot be removed).

If the authenticator already contains one of such a public key credential, the client will throw a [`DOMException`](../domexception) or asks the user if they want to create a new credential.

## Examples

    var publicKey = {
      excludeCredentials: [
        {
          type: "public-key",
          // the id for john.doe@example.com
          id  : new Uint8Array(26) /* this actually is given by the server */
        },
        {
          type: "public-key",
          // the id for john-doe@example.com
          id : new Uint8Array(26) /* another id */
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
      },
      pubKeyCredParams: [ {
        type: "public-key",
        alg: -7 } ]
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialcreationoptions-excludecredentials">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'excludeCredentials' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`excludeCredentials`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/excludeCredentials" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/excludeCredentials</a>

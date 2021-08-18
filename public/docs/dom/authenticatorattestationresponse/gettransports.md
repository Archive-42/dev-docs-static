# AuthenticatorAttestationResponse.getTransports()

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`getTransports()` is a method of the [`AuthenticatorAttestationResponse`](../authenticatorattestationresponse) interface that returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) containing strings describing the different transports which may be used by the authenticator.

Such transports may be USB, NFC, BLE or internal (applicable when the authenticator is not removable from the device).

**Note:** An `AuthenticatorAttestationResponse` instance is available on [`PublicKeyCredential.response`](../publickeycredential/response) after calling [`navigator.credentials.create()`](../credentialscontainer/create).

**Note:** This method may only be used in top-level contexts and will not be available in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) for example.

## Syntax

    arrTransports = authenticatorAttestationResponse.getTransports()

### Parameters

None.

### Return value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) containing the different transports supported by the authenticator or nothing if this information is not available.of the processing of the different extensions by the client. The elements of this array are supposed to be in lexicographical order. Their values may be :

- `"usb"`: the authenticator can be contacted via a removable USB link
- `"nfc"`: the authenticator may be used over [NFC (Near Field Communication)](https://en.wikipedia.org/wiki/Near-field_communication)
- `"ble"`: the authenticator may be used over [BLE (Bluetooth Low Energy)](https://en.wikipedia.org/wiki/Bluetooth_Low_Energy)
- `"internal"`: the authenticator is specifically bound to the client device (cannot be removed).

## Examples

    var publicKey = {
      challenge: /* from the server */,
      rp: {
        name: "Example CORP",
        id  : "login.example.com"
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
        var transports = newCredentialInfo.response.getTransports();
        console.table(transports); // may be something like ["internal", "nfc", "usb"]
      }).catch(function (err) {
         console.error(err);
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-authenticatorattestationresponse-gettransports">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'getTransports()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getTransports`

74

79

No

No

No

No

No

74

No

No

No

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAttestationResponse/getTransports" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AuthenticatorAttestationResponse/getTransports</a>

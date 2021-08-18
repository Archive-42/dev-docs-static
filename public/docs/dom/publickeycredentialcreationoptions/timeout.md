# PublicKeyCredentialCreationOptions.timeout

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `timeout` property, of the [`PublicKeyCredentialCreationOptions`](../publickeycredentialcreationoptions) dictionary, represents an hint, given in milliseconds, for the time the script is willing to wait for the completion of the creation operation.

This property is optional and merely is a _hint_ which may be overridden by the browser.

**Note:** An analogous option exists for the fetching operation ([`navigators.credentials.get()`](../credentialscontainer/get)), see [`PublicKeyCredentialRequestOptions.timeout`](../publickeycredentialrequestoptions/timeout).

## Syntax

    timeout = publicKeyCredentialCreationOptions.timeout

### Value

A numerical hint, expressed in milliseconds, giving the time to wait for the creation operation to complete.

## Examples

    var publicKey = {
      timeout: 60000, // Accepting to wait for a minute before giving up.
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
        // send attestation response and client extensions
        // to the server to proceed with the registration
        // of the credential
      }).catch(function (err) {
         console.error(err);
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialcreationoptions-timeout">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'timeout' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`timeout`

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

- [`PublicKeyCredentialRequestOptions.timeout`](../publickeycredentialrequestoptions/timeout), the analogous option property used when fetching a credential.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/timeout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialCreationOptions/timeout</a>

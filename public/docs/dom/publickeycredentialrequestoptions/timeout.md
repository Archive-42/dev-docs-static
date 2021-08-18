# PublicKeyCredentialRequestOptions.timeout

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `timeout` property, of the [`PublicKeyCredentialRequestOptions`](../publickeycredentialrequestoptions) dictionary, represents an hint, given in milliseconds, for the time the script is willing to wait for the completion of the retrieval operation.

This property is optional and merely is a _hint_ which may be overridden by the browser.

**Note:** An analogous option exists for the creation operation ([`navigators.credentials.create()`](../credentialscontainer/create)), see [`PublicKeyCredentialCreationOptions.timeout`](../publickeycredentialcreationoptions/timeout).

## Syntax

    timeout = publicKeyCredentialRequestOptions.timeout

### Value

A numerical hint, expressed in milliseconds, giving the time to wait for the creation operation to complete.

## Examples

    var options = {
      challenge: new Uint8Array([/* bytes sent from the server */]),
      timeout: 6000  // Wait a minute for the fetching operation
                     // and maybe fail if it takes longer
    };

    navigator.credentials.get({ "publicKey": options })
        .then(function (credentialInfoAssertion) {
        // send assertion response back to the server
        // to proceed with the control of the credential
    }).catch(function (err) {
         console.error(err);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredentialrequestoptions-timeout">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
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

67

67

?

48

13

No

## See also

- [`PublicKeyCredentialCreationOptions.timeout`](../publickeycredentialcreationoptions/timeout), the analogous option property used when creating a credential.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/timeout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredentialRequestOptions/timeout</a>

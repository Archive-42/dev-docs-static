PublicKeyCredential.getClientExtensionResults()
===============================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`getClientExtensionResults()` is a method of the [`PublicKeyCredential`](../publickeycredential) interface that returns an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) which contains a map between the extensions identifiers and their results after having being processed by the client.

During the creation or fetching of a `PublicKeyCredential` (respectively via [`navigator.credentials.create()`](../credentialscontainer/create) and [`navigator.credentials.get()`](../credentialscontainer/get)), it is possible to have "custom" processing by the client for different extensions which are respectively given by [`PublicKeyCredentialCreationOptions.extensions`](../publickeycredentialcreationoptions/extensions) and [`PublicKeyCredentialRequestOptions.extensions`](../publickeycredentialrequestoptions/extensions).

**Note:** Extensions are optional and different browsers may recognize different extensions. All extensions are optional for the client to process them: if a browser does not know of a given extension, that will not cause any failure.

**Note:** This method may only be used in top-level contexts and will not be available in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) for example.

Syntax
------

    mapArrayBuffer = publicKeyCredential.getClientExtensionResults()

### Parameters

None.

### Return value

An [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing the result of the processing of the different extensions by the client. This object contains a map between the extensions' identifiers and their results from the processing.

**Warning!** As of March 2019, only `appId` (used during creation with [`PublicKeyCredentialRequestOptions.extensions`](../publickeycredentialrequestoptions/extensions)) is supported by [Chrome](https://bugs.chromium.org/p/chromium/issues/detail?id=818303) and [Edge](https://docs.microsoft.com/en-us/microsoft-edge/dev-guide/windows-integration/web-authentication#api-surface). Firefox does not seem to [support any extension](https://bugzilla.mozilla.org/show_bug.cgi?id=1370728).

Examples
--------

    var publicKey = {
      // Here are the extensions (as "inputs")
      extensions: {
        "loc": true, // This extension has been defined to include location information in attestation
        "uvi": true  // user verification index: how the user was verified
      },
      challenge: new Uint8Array(16) /* from the server */,
      rp: {
        name: "Example CORP",
        id  : "login.example.com"
      },
      user: {
        id: new Uint8Array(16) /* from the server */,
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
        var myBuffer = newCredentialInfo.getClientExtensionResults();
        // myBuffer will contain the result of any of the processing of the "loc" and "uvi" extensions
      }).catch(function (err) {
         console.error(err);
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredential-getclientextensionresults">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'getClientExtensionResults()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getClientExtensionResults`

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

See also
--------

-   [The list of the currently defined extensions](https://www.w3.org/TR/webauthn/#sctn-defined-extensions)
-   [`AuthenticatorAssertionResponse.authenticatorData`](../authenticatorassertionresponse/authenticatordata) which contains the result of the authenticator's extensions processing
-   [`PublicKeyCredentialCreationOptions.extensions`](../publickeycredentialcreationoptions/extensions) which contains the client extensions' input values for the creation of the credential
-   [`PublicKeyCredentialRequestOptions.extensions`](../publickeycredentialrequestoptions/extensions) which contains the client extensions' input values for the retrieval of the credential

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/getClientExtensionResults" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/getClientExtensionResults</a>

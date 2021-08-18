PublicKeyCredential.isUserVerifyingPlatformAuthenticatorAvailable()
===================================================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

`isUserVerifyingPlatformAuthenticatorAvailable()` is a static method of the [`PublicKeyCredential`](../publickeycredential) interface that returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to `true` if a user-verifying platform authenticator is available.

A user-verifying platform authenticator is a kind of multi-factor authenticator that is part of the client device (it is generally not removable) and that involves an action from the user in order to identify them. Common user-verifying platform authenticators include:

-   Touch ID or Face ID (macOS and iOS)
-   Windows Hello (Windows)
-   Device unlock (fingerprint, face, PIN, etc.) on Android

**Note:** This method may only be used in top-level contexts and will not be available in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) for example.

Syntax
------

    PublicKeyCredential.isUserVerifyingPlatformAuthenticatorAvailable()

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or a not a user-verifying platform authenticator is available.

**Note:** This is a static method which is directly called on the [`PublicKeyCredential`](../publickeycredential) interface and not on an instance.

**Note:** In earlier versions of the specification, the boolean also conveyed the consent of the user to disclose such an authenticator existed.

Examples
--------

    PublicKeyCredential.isUserVerifyingPlatformAuthenticatorAvailable()
      .then(function(available){
        if(available){
          // We can proceed with the creation of a PublicKeyCredential
          // with this authenticator
        } else {
          // Use another kind of authenticator or a classical login/password
          // workflow
        }
      }).catch(function(err){
        // Something went wrong
        console.error(err);
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webauthn/#dom-publickeycredential-isuserverifyingplatformauthenticatoravailable">Web Authentication: An API for accessing Public Key Credentials Level 1<br />
<span class="small">The definition of 'isUserVerifyingPlatformAuthenticatorAvailable' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`isUserVerifyingPlatformAuthenticatorAvailable`

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

-   [Windows Hello](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/windows-hello)
-   [Web Authentication and Windows Hello - MSDN Guide](https://docs.microsoft.com/en-us/microsoft-edge/dev-guide/windows-integration/web-authentication) and especially the [special considerations mentioning `isUserVerifyingPlatformAuthenticator()`](https://docs.microsoft.com/en-us/microsoft-edge/dev-guide/windows-integration/web-authentication#special-considerations-for-windows-hello)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/isUserVerifyingPlatformAuthenticatorAvailable" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PublicKeyCredential/isUserVerifyingPlatformAuthenticatorAvailable</a>

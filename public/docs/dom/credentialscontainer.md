# CredentialsContainer

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `CredentialsContainer` interface of the [Credential Management API](credential_management_api) exposes methods to request credentials and notify the user agent when events such as successful sign in or sign out happen. This interface is accessible from [`Navigator.credentials`](navigator/credentials).

## Properties

None.

### Event handlers

None.

## Methods

[`CredentialsContainer.create()`](credentialscontainer/create)<span class="notecard inline secure">Secure context</span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a new [`Credential`](credential) instance based on the provided options, or `null` if no `Credential` object can be created. In exceptional circumstances, the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) may reject.

[`CredentialsContainer.get()`](credentialscontainer/get)<span class="notecard inline secure">Secure context</span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with the [`Credential`](credential) instance that matches the provided parameters.

[`CredentialsContainer.preventSilentAccess()`](credentialscontainer/preventsilentaccess)<span class="notecard inline secure">Secure context</span>  
Sets a flag that specifies whether automatic log in is allowed for future visits to the current origin, then returns an empty [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). For example, you might call this, after a user signs out of a website to ensure that they aren't automatically signed in on the next site visit. Earlier versions of the spec called this method `requireUserMediation()`. See [Browser compatibility](#browser_compatibility) for support details.

[`CredentialsContainer.store()`](credentialscontainer/store)<span class="notecard inline secure">Secure context</span>  
Stores a set of credentials for a user, inside a provided [`Credential`](credential) instance and returns that instance in a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Examples

    // TBD

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/">Credential Management Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webauthn/">Web Authentication: An API for accessing Public Key Credentials Level 1</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CredentialsContainer`

51

18

61

No

38

13

51

51

61

41

13

5.0

`create`

60

18

61

No

47

13

60

60

61

44

13

8.0

`get`

51

18

61

No

38

13

51

51

61

41

13

5.0

`preventSilentAccess`

60

51-60

18

61

No

47

38-47

13

60

51-60

60

51-60

61

44

41-44

13

8.0

5.0-8.0

`store`

51

79

61

No

38

13

51

51

61

41

13

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer</a>

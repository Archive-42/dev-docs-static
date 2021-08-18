# CredentialsContainer.preventSilentAccess()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `preventSilentAccess()` method of the [`CredentialsContainer`](../credentialscontainer) interface sets a flag that specifies whether automatic log in is allowed for future visits to the current origin, then returns an empty [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). For example, you might call this, after a user signs out of a website to ensure that they aren't automatically signed in on the next site visit. Mediation varies by origin, and is an added check point of browser stored credentials, informing a user of an account login status. This method is typically called after a user signs out of a website, ensuring this user's login information is not automatically passed on the next site visit.

Earlier versions of the spec called this method `requireUserMediation()`. See [Browser compatibility](../credentialscontainer#browser_compatibility) for support details.

## Syntax

    var Promise = CredentialsContainer.preventSilentAccess()

### Parameters

None.

Returns

An empty [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/#dom-credentialscontainer-preventsilentaccess">Credential Management Level 1<br />
<span class="small">The definition of 'preventSilentAccess()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer/preventSilentAccess" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer/preventSilentAccess</a>

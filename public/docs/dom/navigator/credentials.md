Navigator.credentials
=====================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `credentials` property of the [`Navigator`](../navigator) interface returns the [`CredentialsContainer`](../credentialscontainer) interface, which exposes methods to request credentials. The [`CredentialsContainer`](../credentialscontainer) interface also notifies the user agent when an interesting event occurs, such as a successful sign-in or sign-out. This interface can be used for feature detection.

Syntax
------

    var credentialsContainer = navigator.credentials

### Value

The [`CredentialsContainer`](../credentialscontainer) interface.

Example
-------

    if ('credentials' in navigator) {
      navigator.credentials.get({password: true})
      .then(function(creds) {
        //Do something with the credentials.
      });
    } else {
      //Handle sign-in the way you did before.
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/">Credential Management Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`credentials`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/credentials" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/credentials</a>

PasswordCredential
==================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The interface of the [Credential Management API](credential_management_api) provides information about a username/password pair. In supporting browsers an instance of this class may be passed in the `credential` member of the `init` object for global [`WindowOrWorkerGlobalScope.fetch`](windoworworkerglobalscope/fetch).

**Note:** This interface is restricted to top-level contexts and cannot be used from an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe).

Constructor
-----------

 [`PasswordCredential()`](passwordcredential/passwordcredential)<span class="notecard inline secure">Secure context</span>   
Creates a new `PasswordCredential` object.

Properties
----------

*Inherits properties from its ancestor, [`Credential`](credential).*

 [`PasswordCredential.iconURL`](passwordcredential/iconurl) <span class="badge inline readonly">Read only </span><span class="notecard inline secure">Secure context</span>   
A [`USVString`](usvstring) containing a URL pointing to an image for an icon. This image is intended for display in a credential chooser. The URL must be accessible without authentication.

 [`PasswordCredential.name`](passwordcredential/name) <span class="badge inline readonly">Read only </span><span class="notecard inline secure">Secure context</span>   
A [`USVString`](usvstring) containing a human-readable public name for display in a credential chooser.

 [`PasswordCredential.password`](passwordcredential/password) <span class="badge inline readonly">Read only </span><span class="notecard inline secure">Secure context</span>   
A [`USVString`](usvstring) containing the password of the credential.

### Event handlers

None.

Methods
-------

None.

Examples
--------

    var cred = new PasswordCredential({
      id: id,
      password: password,
      name: name,
      iconURL: iconUrl
    });

    navigator.credentials.store(cred)
     .then(function() {
     // Do something else.
    });

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

`PasswordCredential`

51

79

No

No

38

No

51

51

No

41

No

5.0

`PasswordCredential`

51

79

No

No

38

No

51

51

No

41

No

5.0

`iconURL`

51

79

No

No

38

No

51

51

No

41

No

5.0

`name`

51

79

No

No

38

No

51

51

No

41

No

5.0

`password`

60

79

No

No

47

No

60

60

No

44

No

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PasswordCredential" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PasswordCredential</a>

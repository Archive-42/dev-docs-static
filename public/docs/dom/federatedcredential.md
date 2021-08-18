FederatedCredential
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `FederatedCredential` interface of the [Credential Management API](credential_management_api) provides information about credentials from a federated identity provider. A federated identity provider is an entity that a website trusts to correctly authenticate a user, and that provides an API for that purpose. [OpenID Connect](https://openid.net/developers/specs/) is an example of a federated identity provider framework.

In browsers that support it, an instance of this interface may be passed in the `credential` member of the `init` object for global [`WindowOrWorkerGlobalScope.fetch`](windoworworkerglobalscope/fetch).

Constructor
-----------

[`FederatedCredential()`](federatedcredential/federatedcredential)  
Creates a new `FederatedCredential` object.

Properties
----------

*Inherits properties from its ancestor, [`Credential`](credential).*

 [`FederatedCredential.provider`](federatedcredential/provider) <span class="badge inline readonly">Read only </span>   
Returns a [`USVString`](usvstring) containing a credential's federated identity provider.

 [`FederatedCredential.protocol`](federatedcredential/protocol) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) containing a credential's federated identity protocol.

### Event handlers

None.

Methods
-------

None.

Examples
--------

    var cred = new FederatedCredential({
      id: id,
      name: name,
      provider: 'https://account.google.com',
      iconURL: iconUrl
    });

    // Store it
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

`FederatedCredential`

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

`FederatedCredential`

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

`name`

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

`protocol`

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

`provider`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FederatedCredential" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FederatedCredential</a>

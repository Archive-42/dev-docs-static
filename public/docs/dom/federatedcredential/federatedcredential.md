FederatedCredential
===================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `FederatedCredential` constructor creates a new [`FederatedCredential`](../federatedcredential) object. In supporting browsers, an instance of this class may be passed the `credential` received from the `init` object for global [`WindowOrWorkerGlobalScope.fetch`](../windoworworkerglobalscope/fetch).

Syntax
------

    var myCredential = new FederatedCredential(init)

### Parameters

 *init*   
Options are:

-   `provider`: A [`USVString`](../usvstring); identifying the credential provider.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FederatedCredential/FederatedCredential" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FederatedCredential/FederatedCredential</a>

# CredentialsContainer.store()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `store()` method of the [`CredentialsContainer`](../credentialscontainer) stores a set of credentials for the user inside a [`Credential`](../credential) instance, returning this in a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).

This method is restricted to top-level contexts. Calls to it within an `<iframe>` element will resolve without effect.

## Syntax

    CredentialsContainer.store(Credential).then(function(Credential) { ... } )

### Parameters

Credentials  
A valid [`Credential`](../credential) instance.

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), resolving to the passed [`Credential`](../credential) instance.

## Example

### Storing a password credential at successful authentication

This code would be executed after a user signs up or logs in and the server confirms the credential is correct.

    // Check if the browser supports password credentials (and the Credential Management API)
    if ("PasswordCredential" in window) {
      let credential = new PasswordCredential({
        id: "example-username",
        name: "John Doe", // In case of a login, the name comes from the server.
        password: "correct horse battery staple"
      });

      navigator.credentials.store(credential).then(() => {
        console.info("Credential stored in the user agent's credential manager.");
      }, (err) => {
        console.error("Error while storing the credential: ", err);
      });
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/">Credential Management Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer/store" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CredentialsContainer/store</a>

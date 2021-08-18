# PasswordCredential

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `PasswordCredential` constructor creates a new [`PasswordCredential`](../passwordcredential) object. In supporting browsers, an instance of this class may be passed the `credential` from the `init` object for global [`WindowOrWorkerGlobalScope.fetch`](../windoworworkerglobalscope/fetch).

## Syntax

    var myCredential = new PasswordCredential(passwordCredentialData)
    var myCredential = new PasswordCredential(HTMLFormElement)

### Parameters

Either of the following:

_passwordCredentialData_  
A PasswordCredentialData dictionary containing the following fields:

- `iconURL`: (Optional) the URL of a user's avatar image.
- `id`: The ID of the user signing in.
- `name`: (Optional) The name of the user signing in.
- `password`: The password of the user signing in.

_htmlFormElement_  
A reference to an [`HTMLFormElement`](../htmlformelement) with appropriate input fields. The form should, at the very least, contain an id and password. It could also require a CSRF token.

## Examples

This example shows how to set up an [`HTMLFormElement`](../htmlformelement) to caputure data which we'll use to create a [`PasswordCredential`](../passwordcredential) object.

Starting with the form element.

    <form id="form" method="post">
      <input type="text" name="id" autocomplete="username" />
      <input type="password" name="password" autocomplete="current-password" />
      <input type="hidden" name="csrf_token" value="*****" />
    </form>

Then, a reference to this form element, using it to create a [`PasswordCredential`](../passwordcredential) object, and storing it in the browser's password system.

    var form = document.querySelector('#form');
    var creds = new PasswordCredential(form);
    // Store the credentials.
    navigator.credentials.store(creds)
      .then(function(creds) {
      // Do something with the credentials if you need to.
    });

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PasswordCredential/PasswordCredential" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PasswordCredential/PasswordCredential</a>

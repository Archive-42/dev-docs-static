# ContactsManager.getProperties()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `getProperties()` method of the [`ContactsManager`](../contactsmanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) indicating which contact properties are available.

## Syntax

    var ContactProperties = ContactsManager.getProperties();

### Parameters

This method receives no parameters.

### Return value

Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which when resolved returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of available contact properties as [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).

Properties can be any of the following:

- `'name'`: The contact's name.
- `'tel'`: The telephone number(s) of the contact.
- `'email'`: The email address of the contact.
- `'address'`: The contact's postal address.
- `'icon'`: The avatar of the contact.

### Exceptions

No exceptions are thrown.

## Examples

The following asynchronous function uses the `getProperties` method to check for supported properties.

    async function checkProperties() {
      const supportedProperties = await navigator.contacts.getProperties();
      if (supportedProperties.includes('name')) {
        // run code for name support
      }
      if (supportedProperties.includes('email')) {
        // run code for email support
      }
      if (supportedProperties.includes('tel')) {
        // run code for telephone number support
      }
      if (supportedProperties.includes('address')) {
        // run code for address support
      }
      if (supportedProperties.includes('icon')) {
        // run code for avatar support
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/contact-api/spec/#dom-contactsmanager-getproperties">Contact Picker API<br />
<span class="small">The definition of 'getProperties' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getProperties`

No

No

No

No

Yes

No

80

80

No

57

No

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContactsManager/getProperties" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContactsManager/getProperties</a>

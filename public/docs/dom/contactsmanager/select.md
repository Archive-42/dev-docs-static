# ContactsManager.select()

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `select()` method of the [`ContactsManager`](../contactsmanager) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which, when resolved, presents the user with a contact picker which allows them to select contact(s) they wish to share. This method requires a user gesture for the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) to resolve.

## Syntax

    var ContactInfo = ContactsManager.select(properties, options);

### Parameters

_properties_  
An array of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) defining what information to retrieve from a contact. Allowed values are as follows:

- `'name'`: The contact's name.
- `'tel'`: The telephone number(s) of the contact.
- `'email'`: The email address of the contact.
- `'address'`: The contact's postal address.
- `'icon'`: The avatar of the contact.

`options` <span class="badge inline optional">Optional</span>  
Options are as follows:

- `multiple`: A Boolean that allows multiple contacts to be selected. The default is `false`.

### Return value

Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves on successful contact selection.

### Exceptions

`InvalidStateError`  
The browsing context is not top-level or the contact picker is showing a flag. A flag denotes an already existing contact picker, only one picker can exist at any time.

`SecurityError`  
If the method is not triggered by user interaction.

`TypeError`  
If `properties` is empty, or if any of the specified properties are not supported.

## Examples

The following example sets an array of properties to be retrieved for each contact, as well as setting an options object to allow for multiple contacts to be selected.

An asynchronous function is then defined which uses the `select()` method to present the user with a contact picker interface and handle the chosen results.

    const props = ['name', 'email', 'tel', 'address', 'icon'];
    const opts = {multiple: true};

    async function getContacts() {
      try {
          const contacts = await navigator.contacts.select(props, opts);
          handleResults(contacts);
      } catch (ex) {
          // Handle any errors here.
      }
    }

`handleResults()` is a developer defined function.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/contact-api/spec/#contacts-manager-select">Contact Picker API<br />
<span class="small">The definition of 'select' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`select`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContactsManager/select" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContactsManager/select</a>

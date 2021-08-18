# ContactsManager

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `ContactsManager` interface of the [`Contact Picker API`](contact_picker_api) allows users to select entries from their contact list and share limited details of the selected entries with a website or application.

The `ContactsManager` is available through the global [`navigator.contacts`](navigator/contacts) property.

## Methods

[`select()`](contactsmanager/select)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which, when resolved, presents the user with a contact picker which allows them to select contact(s) they wish to share.

[`getProperties()`](contactsmanager/getproperties)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves with an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`strings`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) indicating which contact properties are available.

## Examples

### Feature Detection

The following code checks whether the Contact Picker API is supported.

    const supported = ('contacts' in navigator && 'ContactsManager' in window);

### Checking for Supported Properties

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

### Selecting Contacts

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/contact-api/spec/#contacts-manager">Contact Picker API<br />
<span class="small">The definition of 'ContactsManager' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ContactsManager`

No

No

No

No

57

No

80

80

No

Yes

No

13.0

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

## See also

- [A Contact Picker for the Web](https://web.dev/contact-picker/)
- [A Contact Picker demo on glitch](https://contact-picker.glitch.me/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ContactsManager" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ContactsManager</a>

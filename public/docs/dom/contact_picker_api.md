# Contact Picker API

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The Contact Picker API allows users to select entries from their contact list and share limited details of the selected entries with a website or application.

**Note:** This API is _not available_ in [Web Workers](web_workers_api) (not exposed via [`WorkerNavigator`](workernavigator)).

The Contact Picker API should not be confused with the deprecated [Contact API](https://developer.mozilla.org/docs/Archive/B2G_OS/API/Contacts_API).

## Contact Picker API Concepts and Usage

Access to contacts has long been a feature available within native applications. The Contacts Picker API brings that functionality to web applications.

Use cases include selecting contacts to message via an email or chat application, selecting a contacts phone number for use with voice over IP (VOIP), or for discovering contacts who have already joined a social platform. User agents can also offer a consistent experience with other applications on a users device.

When calling the [`select`](contactsmanager/select) method of the [`ContactsManager`](contactsmanager) interface, the user is presented with a contact picker, whereby they can then select contact information to share with the web application. User interaction is required before permission to display the contact picker is granted and access to contacts is not persistent; the user must grant access every time a request is made by the application.

This API is only available from a secure top-level browsing context and very carefully considers the sensitivity and privacy of contact data. The onus is on the user for choosing data to share and only allows specific data for selected contacts, with no access to any data for other contacts.

## Interfaces

[`ContactsManager`](contactsmanager)  
The `ContactsManager` interface provides a way for users to select and share limited details of contacts with a web application.

[`Navigator.contacts`](navigator/contacts)  
Returns a [`ContactsManager`](contactsmanager) object instance, from which all other functionality can be accessed.

## Examples

### Feature Detection

The following code checks whether the Contact Picker API is supported.

    const supported = 'contacts' in navigator;

### Checking for Supported Properties

The following asynchronous function uses the `getProperties()` method to check for supported properties.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/contact-api/spec/">Contact Picker API</a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Contact_Picker_API`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Contact_Picker_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Contact_Picker_API</a>

Navigator.contacts
==================

**Draft**

This page is not complete.

The `contacts` read-only property of the [`Navigator`](../navigator) interface returns a [`ContactsManager`](../contactsmanager) interface which allows users to select entries from their contact list and share limited details of the selected entries with a website or application.

Syntax
------

    var contactsManager = navigator.contacts;

### Return Value

[`ContactsManager`](../contactsmanager)

Examples
--------

The following code checks whether the Contact Picker API is supported.

    const supported = ('contacts' in navigator && 'ContactsManager' in window);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/contact-api/spec/#extensions-to-navigator">Contact Picker API<br />
<span class="small">The definition of 'Navigator.contacts' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`contacts`

No

No

No

No

No

No

80

80

No

57

No

13.0

See also
--------

-   [A Contact Picker for the Web](https://web.dev/contact-picker/)
-   [A Contact Picker demo on glitch](https://contact-picker.glitch.me/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/contacts" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/contacts</a>

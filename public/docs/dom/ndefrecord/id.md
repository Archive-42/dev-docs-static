NDEFRecord.id
=============

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `id` property ofthe [`NDEFRecord`](../ndefrecord) interface is [`USVString`](../usvstring) containing the record identifier.

This identifier is created by the generator of the record which is solely responsible for enforcing record identifier uniqueness. Web NFC does not sign the NFC content, thus record consumer should not make any assumptions about integrity or authenticity of the identifier or any other part of the records.

Syntax
------

    NDEFRecord.id

### Value

A [`USVString`](../usvstring).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefrecord-id">Web NFC, NDEFRecord</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

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

`id`

No

No

No

No

No

No

No

89

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/id</a>

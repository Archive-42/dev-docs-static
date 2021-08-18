Web NFC API
===========

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Web NFC API allows exchanging data over NFC via light-weight NFC Data Exchange Format (NDEF) messages.

**Note:** Devices and tags have to be formatted and recorded specifically to support NDEF record format to be used with Web NFC. Low-level operations are currently not supported by the API, however there is a public discussion about API that would add such functuionality.

Interfaces
----------

[`NDEFMessage`](ndefmessage)  
Interface that represents NDEF messages that can be received from or sent to a compatible tag via a `NDEFReader` object. A message is composed of metadata and NDEF Records.

[`NDEFReader`](ndefreader)  
Interface that enables reading and writing messages from compatible NFC tags. The messages are represented as `NDEFMessage` objects.

[`NDEFRecord`](ndefrecord)  
Interface that represents NDEF records that can be included in an NDEF message.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/">Web NFC</a></td><td>Draft</td><td></td></tr></tbody></table>

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

`Web_NFC_API`

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

`NDEFReader`

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

`onreading`

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

`onreadingerror`

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

`scan`

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

`secure_context_required`

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

`write`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_NFC_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_NFC_API</a>

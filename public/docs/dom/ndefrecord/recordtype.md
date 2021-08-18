NDEFRecord.recordType
=====================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `recordType` property ofthe [`NDEFRecord`](../ndefrecord) interface is [`USVString`](../usvstring) containing the NDEF record type.

Syntax
------

    NDEFRecord.recordType

### Value

A [`USVString`](../usvstring) which can be one of the following:

`"empty"`  
Represents a empty NDEF record.

`"text"`  
Represents a text NDEF record.

`"url"`  
Represents an URI NDEF record.

`"smart-poster"`  
Represents a "smart poster" NDEF record.

`"absolute-url"`  
Represents an absolute URL NDEF record.

`"mime"`  
Represents a [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) NDEF record.

`"unknown"`  
Represents an unknown NDEF record.

local type name  
Represents a local type name, frequently used to specify NDEF record embedded within another record.

external type name  
Represents a custom record type name that can be creted by organizations themselves for custom needs.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefrecord-recordtype">Web NFC, NDEFRecord.recordType</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

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

`recordType`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/recordType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/recordType</a>

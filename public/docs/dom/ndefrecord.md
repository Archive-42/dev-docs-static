NDEFRecord
==========

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NDEFRecord` interface of the [Web NFC API](web_nfc_api) is an abstract interface that represents data that can be read from or written to compatible NFC devices, e.g. NFC tags supporting NDEF.

Constructor
-----------

 [`NDEFRecord()`](ndefrecord/ndefrecord) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a new `NDEFRecord` with configuration specified in the parameters or default ones if no parameters are specified.

Attributes
----------

 [`NDEFRecord.recordType`](ndefrecord/recordtype) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Represents the NDEF record type.

 [`NDEFRecord.mediaType`](ndefrecord/mediatype) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Represents the [MIME type](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) of the NDEF record payload.

 [`NDEFRecord.id`](ndefrecord/id) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Represents the identificator of the record.  
**Note:** the uniqueness of the identifier is enforced only by the generator of the record.

 [`NDEFRecord.data`](ndefrecord/data) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Represents the payload of the record.

 [`NDEFRecord.encoding`](ndefrecord/encoding) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Represents the encoding name used for encoding the payload in the case it is textual data.

 [`NDEFRecord.lang`](ndefrecord/lang) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Represents a language tag of the content, if it was encoded.

Methods
-------

 [`NDEFRecord.toRecords()`](ndefrecord/torecords) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Coverts [`NDEFRecord.data`](ndefrecord/data) to sequence of records.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefrecord">Web NFC, NDEFRecord</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

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

`NDEFRecord`

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

`NDEFRecord`

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

`data`

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

`encoding`

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

`lang`

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

`mediaType`

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

`toRecords`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord</a>

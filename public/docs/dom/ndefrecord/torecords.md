NDEFRecord.toRecords()
======================

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `toRecords()` method of the [`NDEFRecord`](../ndefrecord) interface of [Web NFC API](../webnfc_api) parses record payload [`NDEFRecord.data`](data) besed on [`NDEFRecord.recordType`](recordtype) and returns the result.

In practice, it's possible to implement the parsing mechanism manually, but this method simplifies the process.

Syntax
------

    NDEFRecord.toRecords()

### Parameters

None.

### Return value

A list of [`NDEFRecord`](../ndefrecord)s.

Exceptions
----------

`NotSupported`  
The [User Agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) does not know how to parse this combination of [`NDEFRecord.data`](data) and [`NDEFRecord.recordType`](recordtype).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefrecord-torecords">Web NFC, NDEFRecord.toRecords()</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/toRecords" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/toRecords</a>

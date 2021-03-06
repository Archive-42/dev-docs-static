# NDEFRecord.encoding

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `encoding` property ofthe [`NDEFRecord`](../ndefrecord) interface is [`USVString`](../usvstring) containing the name of the encoding used to encode NDEF payload if it contains textual data.

## Syntax

    NDEFRecord.encoding

### Value

A [`USVString`](../usvstring) which can be one of the following: `"utf-8"`, `"utf-16"`, `"utf-16le"` or `"utf-16be"`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefrecord-encoding">Web NFC, NDEFRecord.encoding</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/encoding" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/encoding</a>

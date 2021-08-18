NDEFRecord.lang
===============

**Draft**

This page is not complete.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `lang` property ofthe [`NDEFRecord`](../ndefrecord) interface is [`USVString`](../usvstring) containing the <span class="page-not-created">language tag</span> of the record contents, if it is a vailable.

The record might be missing a language tag, for example, if the recorded information is not locale-specific.

Syntax
------

    NDEFRecord.lang

### Value

A [`USVString`](../usvstring).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-nfc/#dom-ndefrecord-lang">Web NFC, NDEFRecord.lang</a></td><td>Draft</td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [HTML `lang` attribute](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/lang), that declares content langauge of the document or its elements
-   HTTP headers that declare content language: [`Content-Language`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Language) and [`Accept-Language`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Language)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/lang" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NDEFRecord/lang</a>

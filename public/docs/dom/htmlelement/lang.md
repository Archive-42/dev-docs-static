HTMLElement.lang
================

The `HTMLElement.lang` property gets or sets the base language of an element's attribute values and text content.

The language code returned by this property is defined in the [*Tags for Identifying Languages (BCP47)*](https://www.ietf.org/rfc/bcp/bcp47.txt) IETF document. Common examples include "en" for English, "ja" for Japanese, "es" for Spanish and so on. The default value of this attribute is `unknown`. Note that this attribute, though valid at the individual element level described here, is most often specified for the root element of the document.

This also only works with the `lang` attribute and not with `xml:lang`.

Syntax
------

    var languageUsed = elementNodeReference.lang; // Get the value of lang
    elementNodeReference.lang = NewLanguage; // Set new value for lang

languageUsed is a string variable that gets the language in which the text of the current element is written. NewLanguage is a string variable with its value setting the language in which the text of the current element is written.

Example
-------

    // this snippet compares the base language and
    // redirects to another url based on language
    if (document.documentElement.lang === "en") {
      window.location.href = "Some_document.html.en";
    } else if (document.documentElement.lang === "ru") {
      window.location.href = "Some_document.html.ru";
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-59132807">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'lang' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/lang" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/lang</a>

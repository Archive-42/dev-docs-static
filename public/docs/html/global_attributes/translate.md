translate
=========

The `translate` [global attribute](../global_attributes) is an enumerated attribute that is used to specify whether an element's *translateable attribute* values and its [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text) node children should be translated when the page is localized, or whether to leave them unchanged. It can have the following values:

-   empty string or "`yes`", which indicates that the element should be translated when the page is localized.
-   "`no`", which indicates that the element must not be translated.

Although not all browsers recognize this attribute, it is respected by automatic translation systems such as Google Translate, and may also be respected by tools used by human translators. As such it's important that web authors use this attribute to mark content that should not be translated.

Examples
--------

In this example, the `translate` attribute is used to ask translation tools not to translate the company's brand name in the footer.

    <footer>
      <small>© 2020 <span translate="no">BrandName</span></small>
    </footer>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#attr-translate">HTML Living Standard<br />
<span class="small">The definition of 'translate' in that specification.</span></a></td></tr></tbody></table>

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

`translate`

19

79

No

No

15

6

4.4

25

No

14

6

1.5

See also
--------

-   All [global attributes](../global_attributes).
-   The <span class="page-not-created">`HTMLElement.translate`</span> property that reflects this attribute.
-   [Using HTML's translate attribute](https://www.w3.org/International/questions/qa-translate-flag).
-   HTML [`lang`](../global_attributes#attr-lang) attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/translate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/translate</a>

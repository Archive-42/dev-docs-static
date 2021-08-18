ShadowRoot.styleSheets
======================

The `styleSheets` read-only property of the [`ShadowRoot`](../shadowroot) interface returns a [`StyleSheetList`](../stylesheetlist) of [`CSSStyleSheet`](../cssstylesheet) objects, for stylesheets explicitly linked into or embedded in a shadow tree.

Syntax
------

    shadowRoot.styleSheets

### Value

A [`StyleSheetList`](../stylesheetlist) of [`CSSStyleSheet`](../cssstylesheet) objects.

Examples
--------

    let customElem = document.querySelector('my-shadow-dom-element');
    let shadow = customElem.shadowRoot;
    let styleSheets = shadow.styleSheets;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#extensions-to-the-document-or-shadow-root-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'DocumentOrShadowRoot.styleSheets' in that specification.</span></a></td></tr></tbody></table>

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

`styleSheets`

53

79

63

No

40

12.1

53

53

63

41

12.2

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/styleSheets" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot/styleSheets</a>

StyleSheet.parentStyleSheet
===========================

The `parentStyleSheet` property of the [`StyleSheet`](../stylesheet) interface returns the style sheet, if any, that is including the given style sheet.

Syntax
------

    objRef = stylesheet.parentStyleSheet

Example
-------

    // Find the top level stylesheet
    if (stylesheet.parentStyleSheet) {
      sheet = stylesheet.parentStyleSheet;
    } else {
      sheet = stylesheet;
    }

Notes
-----

This property returns `null` if the current stylesheet is a top-level stylesheet or if stylesheet inclusion is not supported.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-stylesheet-parentstylesheet">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'StyleSheet: parentStyleSheet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`parentStyleSheet`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/parentStyleSheet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/parentStyleSheet</a>

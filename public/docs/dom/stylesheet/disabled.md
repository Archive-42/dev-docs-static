StyleSheet.disabled
===================

The `disabled` property of the [`StyleSheet`](../stylesheet) interface determines whether the style sheet is prevented from applying to the document.

A style sheet may be disabled by manually setting this property to `true` or if it's an inactive [alternative style sheet](https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets). Note that `disabled == false` does not guarantee the style sheet is applied (it could be removed from the document, for instance).

Syntax
------

    bool = stylesheet.disabled

Example
-------

    // If the stylesheet is disabled...
    if (stylesheet.disabled) {
      // ... apply styles in-line.
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-stylesheet-disabled">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'StyleSheet.disabled' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/stylesheets.html#StyleSheets-StyleSheet-disabled">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'StyleSheet.disabled' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`disabled`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/disabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/disabled</a>

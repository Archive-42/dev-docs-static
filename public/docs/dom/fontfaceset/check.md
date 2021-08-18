FontFaceSet.check()
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `check()` method of the [`FontFaceSet`](../fontfaceset) returns whether all fonts in the given font list have been loaded and are available.

Syntax
------

    bool = aFontFaceSet.check(font);
    bool = aFontFaceSet.check(font, text);

### Returns

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is true if the font list is available

### Parameters

-   `font`: a font specification using the [CSS value syntax](https://developer.mozilla.org/en-US/docs/Web), e.g. "italic bold 16px Roboto"
-   `text`: limit the font faces to those whose Unicode range contains at least one of the characters in text. This [does not check for individual glyph coverage](https://lists.w3.org/Archives/Public/www-style/2015Aug/0330.html).

Examples
--------

    document.fonts.check("12px courier"); // returns true if the font courier is available at 12px

    document.fonts.check("12px MyFont", "ß"); // returns true if the font 'MyFont' has a ß character.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#font-face-set-check">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'check' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`check`

35

≤79

41

No

?

10

37

35

41

?

Yes

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet/check" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet/check</a>

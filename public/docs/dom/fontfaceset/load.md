FontFaceSet.load()
==================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `load()` method of the [`FontFaceSet`](../fontfaceset) forces all the fonts given in parameters to be loaded.

Syntax
------

    result = aFontFaceSet.load(font);

    result = aFontFaceSet.load(font, text);

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) of an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of <span class="page-not-created">`FontFace`</span> loaded. The promise is fulfilled when all the fonts are loaded; it is rejected if one of the fonts failed to load.

### Parameters

-   `font`: a font specification using the [CSS value syntax](https://developer.mozilla.org/en-US/docs/Web), e.g. "italic bold 16px Roboto"
-   `text`: limit the font faces to those whose Unicode range contains at least one of the characters in text. This [does not check for individual glyph coverage](https://lists.w3.org/Archives/Public/www-style/2015Aug/0330.html).

Examples
--------

    // returns a promise that will be fulfilled or rejected according the success to load MyFont
    // The code in 'then' can assume the availability of that font.

    document.fonts.load("12px MyFont", "ß").then(…);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#font-face-set-load">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'load' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`load`

35

≤79

41

No

35

10

37

35

41

35

Yes

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet/load" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet/load</a>

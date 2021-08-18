# FontFace.unicodeRange

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `unicodeRange` property of the [`FontFace`](../fontface) interface retrieves or sets the range of unicode codepoints encompassing the font. It is equivalent to the [`unicode-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range) descriptor.

## Syntax

    var unicodeRangeDescriptor = FontFace.unicodeRange;
    FontFace.unicodeRange = unicodeRangeDescriptor;

### Value

A [`CSSOMString`](../cssomstring) containing a descriptor as it would appear in a style sheet's `@font-face` rule.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#dom-fontface-unicoderange">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'unicodeRange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`unicodeRange`

35

79

Yes

No

Yes

10

37

35

Yes

Yes

10

4.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFace/unicodeRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFace/unicodeRange</a>

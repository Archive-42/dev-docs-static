# FontFace.family

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `FontFace.family` property allows the author to get or set the font family of a [`FontFace`](../fontface) object. This is equivalent to the [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-family) descriptor of [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face).

## Syntax

    instanceOfFontFace.family = 'font family name';
    var fontFace = instanceOfFontFace.family; // "font family name"

### Value

A [`DOMString`](../domstring).

## Example

    var fontFace = new FontFace('Roboto', 'url(https://fonts.example.com/roboto.woff2)');
    console.log(fontFace.family); // 'Roboto'

    fontFace.family = 'newRoboto';
    console.log(fontFace.family); // 'newRoboto'

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#dom-fontface-family">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'family' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`family`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFace/family" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFace/family</a>

# FontFace.FontFace()

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `FontFace()` constructor creates a new [`FontFace`](../fontface) object.

## Syntax

    var fontFace = new FontFace(family, source, descriptors);

### Parameters

_family_  
Specifies a name that will be used as the font face value for font properties. Takes the same type of values as the [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-family) descriptor of [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face) .

_source_  
The font source. This can be either:

- A URL
- Binary font data

descriptors <span class="badge inline optional">Optional</span>  
A set of optional descriptors passed as an object. It can have the following keys:

- `family`: Family
- `style`: Style
- `weight`: Weight
- `stretch`: Stretch
- `unicodeRange`: Unicode range
- `variant`: variant
- `featureSettings`: Feature settings

## Example

    async function loadFonts() {
        const font = new FontFace('myfont', 'url(myfont.woff)');
        // wait for font to be loaded
        await font.load();
        // add font to document
        document.fonts.add(font);
        // enable font with CSS class
        document.body.classList.add('fonts-loaded');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#font-face-constructor">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'FontFace Constructor' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`FontFace`

35

79

41

No

22

10

37

35

41

22

10

4.0

## See also

- [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFace/FontFace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFace/FontFace</a>

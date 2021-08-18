SVGAltGlyphElement.format
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `SVGAltGlyphElement.format` property is a [`DOMString`](../domstring) that defines the format of the given font. It has the same meaning as the 'format' property of [`SVGGlyphRefElement`](../svgglyphrefelement) property. If the font is in one of the formats listed in [CSS2(\[CSS2\], section15.3.5)](https://www.w3.org/TR/2008/REC-CSS2-20080411/fonts.html#referencing), then its value is the corresponding &lt;string&gt; parameter of the font.

Syntax
------

    string = myGlyph.format;
     myGlyph.format = string;

### Value

The format values listed below are taken from [CSS2(\[CSS2\], section15.3.5)](https://www.w3.org/TR/2008/REC-CSS2-20080411/fonts.html#referencing).

<table><thead><tr class="header"><th>String</th><th>Font Format</th><th>Examples of common extensions</th></tr></thead><tbody><tr class="odd"><td>truedoc-pfr</td><td>TrueDoc™ Portable Font Resource</td><td>.pfr</td></tr><tr class="even"><td>embedded-opentype</td><td>Embedded OpenType</td><td>.eot</td></tr><tr class="odd"><td>type-1</td><td>PostScript™ Type 1</td><td>.pfb, .pfa</td></tr><tr class="even"><td>truetype</td><td>TrueType</td><td>.ttf</td></tr><tr class="odd"><td>opentype</td><td>OpenType, including TrueType Open</td><td>.ttf</td></tr><tr class="even"><td>truetype-gx</td><td>TrueType with GX extensions</td><td>-</td></tr><tr class="odd"><td>speedo</td><td>Speedo</td><td>-</td></tr><tr class="even"><td>intellifont</td><td>Intellifont</td><td>-</td></tr></tbody></table>

Example
-------

    myGlyph.format = "truedoc-pfr";

Specifications
--------------

<table><tbody><tr class="odd"><td>Specification</td><td>Status</td><td>Comment</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/#format">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'format' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`format`

1

≤79

4

No

10.6

4

37

18

4

11

3

1.0

See also
--------

-   [`SVGAltGlyphElement`](../svgaltglyphelement)
-   [`SVGGlyphRefElement`](../svgglyphrefelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAltGlyphElement/format" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAltGlyphElement/format</a>

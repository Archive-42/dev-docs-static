SVGAltGlyphElement.glyphRef
===========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `SVGAltGlyphElement.glyphRef` property is a [`DOMString`](../domstring) representing a glyph identifier. It has the same meaning as the ‘glyphRef’ property on the [`SVGGlyphRefElement`](../svgglyphrefelement) interface of the [`<glyphRef>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/glyphRef) element.

Syntax
------

    string = myGlyph.glyphRef;
    myGlyph.glyphRef = string;

### Value

The return value is a Glyph Identifier, the value of which depends on the <span class="page-not-created">`format`</span> of the given font.

Example
-------

    myGlyph.glypRef = "#glyphID";

Specifications
--------------

<table><tbody><tr class="odd"><td>Specification</td><td>Status</td><td>Comment</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/text.html#InterfaceSVGGlyphRefElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'glyphRef' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`glyphRef`

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

-   <span class="page-not-created">`SVGGlyphRef`Element</span>
-   [`SVGAltGlyphElement`](../svgaltglyphelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAltGlyphElement/glyphRef" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAltGlyphElement/glyphRef</a>

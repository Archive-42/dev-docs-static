SVGAltGlyphElement
==================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `SVGAltGlyphElement` interface represents an [`<altglyph>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/altGlyph) element. This interface makes it possible to implement more sophisticated and particular glyph characters. For some textal representations as: ligatures (e.g. æ, ß, etc ), special-purpose fonts (e.g. musical symbols) or even alternate glyphs such as Asian text strings it is required that a different set of glyphs be used than the normal given character data.

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGGraphicsElement`](svggraphicselement).*

 [`SVGAltGlyphElement.glyphRef`](svgaltglyphelement/glyphref) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
It corresponds to the attribute `glyphRef` on the given element. It's data type is 'String'. It defines the glyph identifier, whose format is dependent on the ‘format’ of the given font.

 [`SVGAltGlyphElement.format`](svgaltglyphelement/format) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
It corresponds to the attribute `format` on the given element. It's data type is 'String'. This property specifies the format of the given font.

Methods
-------

*This interface has no methods but inherits methods from its parent, [`SVGElement`](svgelement).*

Specifications
--------------

<table><tbody><tr class="odd"><td>Specification</td><td>Status</td><td>Comment</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/text.html#InterfaceSVGAltGlyphElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGAltGlyphElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGAltGlyphElement`

1

≤79

4

partial support, see [bug 456286](https://bugzil.la/456286) and [bug 571808](https://bugzil.la/571808).

No

10.6

4

37

18

4

partial support, see [bug 456286](https://bugzil.la/456286) and [bug 571808](https://bugzil.la/571808).

11

3

1.0

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

-   SVG [`<altglyph>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/altGlyph) Element

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAltGlyphElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAltGlyphElement</a>

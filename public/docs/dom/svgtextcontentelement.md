SVGTextContentElement
=====================

The `SVGTextContentElement` interface is implemented by elements that support rendering child text content. It is inherited by various text-related interfaces, such as [`SVGTextElement`](svgtextelement), [`SVGTSpanElement`](svgtspanelement), [`SVGTRefElement`](svgtrefelement), [`SVGAltGlyphElement`](svgaltglyphelement) and [`SVGTextPathElement`](svgtextpathelement).

Constants
---------

<table><tbody><tr class="odd"><td>Constant</td><td>Value</td><td>Description</td></tr><tr class="even"><td>LENGTHADJUST_UNKNOWN</td><td>0</td><td>Some other value.</td></tr><tr class="odd"><td>LENGTHADJUST_SPACING</td><td>1</td><td>The <code>spacing</code> keyword.</td></tr><tr class="even"><td>LENGTHADJUST_SPACINGANDGLYPHS</td><td>2</td><td>The <code>spacingAndGlyphs</code> keyword.</td></tr></tbody></table>

Properties
----------

*This interface also inherits properties from its parent, [`SVGGraphicsElement`](svggraphicselement).*

 <span class="page-not-created">`SVGTextContentElement.textLength`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) reflecting the `textLength` attribute of the given element.

 <span class="page-not-created">`SVGTextContentElement.lengthAdjust`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) reflecting the `lengthAdjust` attribute of the given element. The numeric type values represent one of the constant values above.

Methods
-------

*This interface also inherits methods from its parent, [`SVGGraphicsElement`](svggraphicselement).*

<span class="page-not-created">`SVGTextContentElement.getNumberOfChars()`</span>  
Returns a long representing the total number of addressable characters available for rendering within the current element, regardless of whether they will be rendered.

<span class="page-not-created">`SVGTextContentElement.getComputedTextLength()`</span>  
Returns a float representing the computed length for the text within the element.

<span class="page-not-created">`SVGTextContentElement.getSubStringLength()`</span>  
Returns a float representing the computed length of the formatted text advance distance for a substring of text within the element. Note that this method only accounts for the widths of the glyphs in the substring and any extra spacing inserted by the CSS 'letter-spacing' and 'word-spacing' properties. Visual spacing adjustments made by the 'x' attribute is ignored.

<span class="page-not-created">`SVGTextContentElement.getStartPositionOfChar()`</span>  
Returns a [`DOMPoint`](dompoint) representing the position of a typographic character after text layout has been performed.

**Note:** In SVG 1.1 this method returned an [`SVGPoint`](svgpoint).

<span class="page-not-created">`SVGTextContentElement.getEndPositionOfChar()`</span>  
Returns a [`DOMPoint`](dompoint) representing the trailing position of a typographic character after text layout has been performed.

**Note:** In SVG 1.1 this method returned an [`SVGPoint`](svgpoint).

<span class="page-not-created">`SVGTextContentElement.getExtentOfChar()`</span>  
Returns a [`DOMRect`](domrect) representing the computed tight bounding box of the glyph cell that corresponds to a given typographic character.

<span class="page-not-created">`SVGTextContentElement.getRotationOfChar()`</span>  
Returns a float representing the rotation of typographic character.

<span class="page-not-created">`SVGTextContentElement.getCharNumAtPosition()`</span>  
Returns a long representing the character which caused a text glyph to be rendered at a given position in the coordinate system. Because the relationship between characters and glyphs is not one-to-one, only the first character of the relevant typographic character is returned

 <span class="page-not-created">`SVGTextContentElement.selectSubString()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Selects text within the element.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/text.html#InterfaceSVGTextContentElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGTextContentElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Changed inheritance from <a href="svgelement"><code>SVGElement</code></a> to <a href="svggraphicselement"><code>SVGGraphicsElement</code></a> and <code>getStartPositionOfChar()</code> and removed implementations of <a href="svgtests"><code>SVGTests</code></a>, <span class="page-not-created"><code>SVGLangSpace</code></span>, <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a>, <a href="svgstylable"><code>SVGStylable</code></a> interfaces and <code>getEndPositionOfChar()</code> to return a <a href="dompoint"><code>DOMPoint</code></a> instead of an <a href="svgpoint"><code>SVGPoint</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/text.html#InterfaceSVGTextContentElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGTextContentElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGTextContentElement`

1

12

1.5

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`getCharNumAtPosition`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`getComputedTextLength`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`getEndPositionOfChar`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`getExtentOfChar`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`getNumberOfChars`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`getRotationOfChar`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`getStartPositionOfChar`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`getSubStringLength`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`lengthAdjust`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`selectSubString`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`textLength`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGTextContentElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGTextContentElement</a>

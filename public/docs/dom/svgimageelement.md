SVGImageElement
===============

The `SVGImageElement` interface corresponds to the [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image) element.

Properties
----------

*This interface also inherits properties from its parent, [`SVGGraphicsElement`](svggraphicselement).*

<span class="page-not-created">`SVGImageElement.crossOrigin`</span>  
A [`DOMString`](domstring) corresponding to the `crossorigin` attribute of the given [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image) element.

[`SVGImageElement.decoding`](svgimageelement/decoding)  
Returns a [`DOMString`](domstring) representing a hint given to the browser on how it should decode the image.

 [`SVGImageElement.height`](svgimageelement/height) <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `height` attribute of the given [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image) element.

 [`SVGImageElement.preserveAspectRatio`](svgimageelement/preserveaspectratio) <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedPreserveAspectRatio`](svganimatedpreserveaspectratio) corresponding to the `preserveAspectRatio` attribute of the given [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image) element.

 [`SVGImageElement.width`](svgimageelement/width) <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `width` attribute of the given [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image) element.

 [`SVGImageElement.x`](svgimageelement/x) <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `x` attribute of the given [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image) element.

 [`SVGImageElement.y`](svgimageelement/y) <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `y` attribute of the given [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image) element.

Methods
-------

*This interface also inherits methods from its parent interface, [`SVGGraphicsElement`](svggraphicselement).*

[`SVGImageElement.decode()`](svgimageelement/decode)  
Initiates asynchronous decoding of the image data. Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves once the image data is ready to be used.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/embedded.html#InterfaceSVGImageElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGImageElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Changed the inheritance from <a href="svgelement"><code>SVGElement</code></a> to <a href="svggraphicselement"><code>SVGGraphicsElement</code></a>, removed the implemented interfaces <a href="svgtests"><code>SVGTests</code></a>, <span class="page-not-created"><code>SVGLangSpace</code></span>, <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a>, <a href="svgstylable"><code>SVGStylable</code></a>, and <a href="svgtransformable"><code>SVGTransformable</code></a> and added the <code>crossOrigin</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/struct.html#InterfaceSVGImageElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGImageElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGImageElement`

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

`crossOrigin`

No

No

?

No

No

No

No

No

?

No

No

No

`decode`

65

≤79

No

No

52

No

65

65

No

47

No

9.0

`decoding`

65

≤79

63

No

52

No

65

65

63

47

No

9.0

`height`

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

`href`

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

`preserveAspectRatio`

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

`width`

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

`x`

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

`y`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGImageElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGImageElement</a>

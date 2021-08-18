SVGRectElement
==============

The `SVGRectElement` interface provides access to the properties of [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect) elements, as well as methods to manipulate them.

Properties
----------

*This interface also inherits properties from its parent, [`SVGGeometryElement`](svggeometryelement).*

 <span class="page-not-created">`SVGRectElement.x`</span> <span class="badge inline readonly">Read only </span>   
Returns an [`SVGAnimatedLength`](svganimatedlength) corresponding to the `x` attribute of the given [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect) element.

 <span class="page-not-created">`SVGRectElement.y`</span> <span class="badge inline readonly">Read only </span>   
Returns an [`SVGAnimatedLength`](svganimatedlength) corresponding to the `y` attribute of the given [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect) element.

 <span class="page-not-created">`SVGRectElement.width`</span> <span class="badge inline readonly">Read only </span>   
Returns an [`SVGAnimatedLength`](svganimatedlength) corresponding to the `width` attribute of the given [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect) element.

 <span class="page-not-created">`SVGRectElement.height`</span> <span class="badge inline readonly">Read only </span>   
Returns an [`SVGAnimatedLength`](svganimatedlength) corresponding to the `height` attribute of the given [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect) element.

 <span class="page-not-created">`SVGRectElement.rx`</span> <span class="badge inline readonly">Read only </span>   
Returns an [`SVGAnimatedLength`](svganimatedlength) corresponding to the `rx` attribute of the given [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect) element.

 <span class="page-not-created">`SVGRectElement.ry`</span> <span class="badge inline readonly">Read only </span>   
Returns an [`SVGAnimatedLength`](svganimatedlength) corresponding to the `ry` attribute of the given [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect) element.

Methods
-------

*This interface doesn't implement any specific methods, but inherits methods from its parent, [`SVGGeometryElement`](svggeometryelement).*

Example
-------

Here is a simple usage of rect interface. (Changing the color of the rect interface on every click)

### SVG content

    <svg xmlns="http://www.w3.org/2000/svg" version="1.1">
      <rect width="300" height="100" id="myrect" onclick="doRectClick()"
          style="fill:rgb(0,0,255);stroke-width:1;stroke:rgb(0,0,0)" />
      <text x="60" y="40" fill="white" font-size="40"
          onclick="doRectClick();">Click Me</text>
    </svg>

### JavaScript content

    function doRectClick(){
      var myrect = document.getElementById('myrect');
      var r = Math.floor(Math.random() * 255);
      var g = Math.floor(Math.random() * 255);
      var b = Math.floor(Math.random() * 255);
      myrect.style.fill = 'rgb(' + r + ', ' + g + ' , ' + b + ')';
    }

*Click the rect.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/shapes.html#InterfaceSVGRectElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGRectElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Replaced the inheritance from <a href="svgelement"><code>SVGElement</code></a><a href="svgtests"><code>SVGTests</code></a>, <span class="page-not-created"><code>SVGLangSpace</code></span>, <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a>, <a href="svgstylable"><code>SVGStylable</code></a>, and <a href="svgtransformable"><code>SVGTransformable</code></a> by <a href="svggeometryelement"><code>SVGGeometryElement</code></a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/shapes.html#InterfaceSVGRectElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGRectElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGRectElement`

1

12

Before Edge 79, this interface implements only the SVG 1.1 specification.

1.5

Only implements the SVG 1.1 specification of the interface.

9

Only implements the SVG 1.1 specification of the interface.

≤12.1

3

1

18

4

Only implements the SVG 1.1 specification of the interface.

≤12.1

1

1.0

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

`rx`

1

12

1.5

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`ry`

1

12

1.5

9

≤12.1

4

1

18

4

≤12.1

3.2

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

See also
--------

-   [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGRectElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGRectElement</a>

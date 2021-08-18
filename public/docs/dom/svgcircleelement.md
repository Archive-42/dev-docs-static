SVGCircleElement
================

The `SVGCircleElement` interface is an interface for the [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle) element.

Properties
----------

*This interface also inherits properties from its parent, [`SVGGeometryElement`](svggeometryelement).*

 [`SVGCircleElement.cx`](svgcircleelement/cx) <span class="badge inline readonly">Read only </span>   
This property defines the x-coordinate of the center of the [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle) element. It is denoted by the `cx` attribute of the element.

 [`SVGCircleElement.cy`](svgcircleelement/cy) <span class="badge inline readonly">Read only </span>   
This property defines the y-coordinate of the center of the `<circle>` element. It is denoted by the `cy` attribute of the element.

 [`SVGCircleElement.r`](svgcircleelement/r) <span class="badge inline readonly">Read only </span>   
This property defines the radius of the `<circle>` element. It is denoted by the `r` of the element.

Methods
-------

*This interface has no methods but inherits methods from its parent, [`SVGGeometryElement`](svggeometryelement).*

Example
-------

### SVG content

    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250" width="250" height="250">
      <circle cx="100" cy="100" r="50" fill="gold" id="circle"
          onclick="clickCircle();"/>
    </svg>

### JavaScript content

This function `clickCircle()` is called when the circle is clicked. It randomly increases or decreases the radius of the circle element.

    function clickCircle() {
      var circle = document.getElementById("circle");
      // Randomly determine if the circle radius will increase or decrease
      var change = Math.random() > 0.5 ? 10 : -10;
      // Clamp the circle radius to a minimum of 10 and a maximum of 250,
      // so it won't disappear or get bigger than the viewport
      var newValue = Math.min(Math.max(circle.r.baseVal.value + change, 10), 250);
      circle.setAttribute("r", newValue);
    }

*Click on the circle.*  

Specifications
--------------

<table><tbody><tr class="odd"><td>Specification</td><td>Status</td><td>Comment</td></tr><tr class="even"><td><a href="https://svgwg.org/svg2-draft/shapes.html#InterfaceSVGCircleElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGCircleElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Replaced the inheritance from <a href="svgelement"><code>SVGElement</code></a>, <a href="svgtests"><code>SVGTests</code></a>, <span class="page-not-created"><code>SVGLangSpace</code></span>, <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a>, <a href="svgstylable"><code>SVGStylable</code></a>, and <a href="svgtransformable"><code>SVGTransformable</code></a> by <a href="svggeometryelement"><code>SVGGeometryElement</code></a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/SVG11/shapes.html#InterfaceSVGCircleElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGCircleElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGCircleElement`

1

12

1.5

9

8

3

1

18

4

10.1

1

1.0

`cx`

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

`cy`

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

`r`

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

-   [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle) SVG element

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGCircleElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGCircleElement</a>

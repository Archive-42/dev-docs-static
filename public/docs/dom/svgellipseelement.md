SVGEllipseElement
=================

The `SVGEllipseElement` interface provides access to the properties of [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/ellipse) elements.

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGGeometryElement`](svggeometryelement).*

 <span class="page-not-created">`SVGEllipseElement.cx`</span> <span class="badge inline readonly">Read only </span>   
This property returns a [`SVGAnimatedLength`](svganimatedlength) reflecting the `cx` attribute of the given [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/ellipse) element.

 <span class="page-not-created">`SVGEllipseElement.cy`</span> <span class="badge inline readonly">Read only </span>   
This property returns a [`SVGAnimatedLength`](svganimatedlength) reflecting the `cy` attribute of the given [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/ellipse) element.

 <span class="page-not-created">`SVGEllipseElement.rx`</span> <span class="badge inline readonly">Read only </span>   
This property returns a [`SVGAnimatedLength`](svganimatedlength) reflecting the `rx` attribute of the given [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/ellipse) element.

 <span class="page-not-created">`SVGEllipseElement.ry`</span> <span class="badge inline readonly">Read only </span>   
This property returns a [`SVGAnimatedLength`](svganimatedlength) reflecting the `ry` attribute of the given [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/ellipse) element.

Methods
-------

*This interface doesn't implement any specific methods, but inherits methods from its parent interface, [`SVGGeometryElement`](svggeometryelement).*

Example
-------

### SVG content

    <svg width="200" height="200" xmlns="http://www.w3.org/2000/svg">
      <ellipse cx="100" cy="100" rx="100" ry="60" id="ellipse"
          onclick="outputSize();"/>
    </svg>

### JavaScript content

    function outputSize() {
      var ellipse = document.getElementById("ellipse");

      // Outputs "horizontal radius: 100 vertical radius: 60"
      console.log(
        'horizontal radius: ' + ellipse.rx.baseVal.valueAsString,
        'vertical radius: ' + ellipse.ry.baseVal.valueAsString
      )
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/shapes.html#InterfaceSVGEllipseElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGEllipseElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/shapes.html#InterfaceSVGEllipseElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGEllipseElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGEllipseElement`

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

`rx`

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

`ry`

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

-   [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/ellipse) SVG Element

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGEllipseElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGEllipseElement</a>

SVGCircleElement.r
==================

The `r` read-only property of the [`SVGCircleElement`](../svgcircleelement) interface reflects the `r` attribute of a [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle) element and by that defines the radius of the circle. If unspecified, the effect is as if the value is set to `0`.

Syntax
------

    var radius = element.r;

### Value

An [`SVGAnimatedLength`](../svganimatedlength) representing the radius of the circle.

Example
-------

### SVG

    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" width="200" height="200">
      <circle r="50" r="50" r="50" fill="gold" id="circle"/>
    </svg>

### JavaScript

    const circle = document.getElementById('circle');
    console.log(circle.r);

Specifications
--------------

<table><tbody><tr class="odd"><td>Specification</td><td>Status</td><td>Comment</td></tr><tr class="even"><td><a href="https://svgwg.org/svg2-draft/shapes.html#__svg__SVGCircleElement__r">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGCircleElement.r' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/SVG11/shapes.html#__svg__SVGCircleElement__r">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGCircleElement.r' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

-   [`SVGCircleElement.cx`](cx)
-   [`SVGCircleElement.cy`](cy)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGCircleElement/r" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGCircleElement/r</a>

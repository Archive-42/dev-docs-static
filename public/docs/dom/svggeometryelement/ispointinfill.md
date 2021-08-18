SVGGeometryElement.isPointInFill()
==================================

The `SVGGeometryElement.isPointInFill()` method determines whether a given point is within the fill shape of an element. Normal hit testing rules apply; the value of the [`pointer-events`](https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events) property on the element determines whether a point is considered to be within the fill. The `point` argument is interpreted as a point in the local coordinate system of the element.

Syntax
------

    boolean someElement.isPointInFill(DOMPointInit point);

### Parameters

point  
A [`DOMPointInit`](../dompointinit) interpreted as a point in the local coordinate system of the element.

### Return value

A boolean indicating whether the given point is within the fill or not.

Example
-------

### SVG

    <svg viewBox="0 0 100 100" width="150" height="150"
        xmlns="http://www.w3.org/2000/svg">
      <circle id="circle" cx="50" cy="50" r="45"
          fill="white" stroke="black" stroke-width="10"/>

      <circle cx="10" cy="10" r="5" fill="seagreen"/>
      <circle cx="40" cy="30" r="5" fill="seagreen"/>
    </svg>

### JavaScript

    var circle = document.getElementById('circle');

    // Point not in circle
    console.log('Point at 10,10:', circle.isPointInFill(new DOMPoint(10, 10)));

    // Point in circle
    console.log('Point at 40,30:', circle.isPointInFill(new DOMPoint(40, 30)));

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#__svg__SVGGeometryElement__isPointInFill">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGGeometryElement.isPointInFill()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`isPointInFill`

33

79

69

No

20

12

4.4.3

33

79

20

12

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGGeometryElement/isPointInFill" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGGeometryElement/isPointInFill</a>

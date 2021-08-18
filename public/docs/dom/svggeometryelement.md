SVGGeometryElement
==================

The `SVGGeometryElement` interface represents SVG elements whose rendering is defined by geometry with an equivalent path, and which can be filled and stroked. This includes paths and the basic shapes.

Properties
----------

*This interface also inherits properties from its parent, [`SVGGraphicsElement`](svggraphicselement).*

 [`SVGGeometryElement.pathLength`](svggeometryelement/pathlength) <span class="badge inline readonly">Read only </span>   
This property reflects the `pathLength` attribute.

Methods
-------

*This interface also inherits methods from its parent, [`SVGGraphicsElement`](svggraphicselement).*

[`SVGGeometryElement.isPointInFill()`](svggeometryelement/ispointinfill)  
Determines whether a given point is within the fill shape of an element. Normal hit testing rules apply; the value of the [`pointer-events`](https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events) property on the element determines whether a point is considered to be within the fill.

[`SVGGeometryElement.isPointInStroke()`](svggeometryelement/ispointinstroke)  
Determines whether a given point is within the stroke shape of an element. Normal hit testing rules apply; the value of the [`pointer-events`](https://developer.mozilla.org/en-US/docs/Web/CSS/pointer-events) property on the element determines whether a point is considered to be within the stroke.

[`SVGGeometryElement.getTotalLength()`](svggeometryelement/gettotallength)  
Returns the user agent's computed value for the total length of the path in user units.

[`SVGGeometryElement.getPointAtLength()`](svggeometryelement/getpointatlength)  
Returns the point at a given distance along the path.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#InterfaceSVGGeometryElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGGeometryElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGGeometryElement`

56

1-56

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

79

12-79

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

53

1.5-53

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

9

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

43

≤12.1-43

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

12

3-12

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

56

1-56

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

56

18-56

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

53

4-53

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

43

≤12.1-43

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

12

1-12

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

6.0

1.0-6.0

The `SVGGeometryElement` interface itself is not present, but some of its members are available on the [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement) interface.

`getPointAtLength`

56

1-56

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

79

12-79

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

61

1.5-61

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

9

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

43

≤12.1-43

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

12

3-12

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

56

1-56

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

56

18-56

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

61

4-61

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

43

≤12.1-43

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

12

1-12

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

6.0

1.0-6.0

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

`getTotalLength`

56

1-56

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

79

12-79

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

61

1.5-61

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

9

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

43

≤12.1-43

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

12

3-12

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

56

1-56

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

56

18-56

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

61

4-61

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

43

≤12.1-43

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

12

1-12

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

6.0

1.0-6.0

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

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

`isPointInStroke`

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

`pathLength`

57

1-57

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

79

61

1.5-61

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

No

44

≤12.1-44

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

12

3-12

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

57

1-57

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

57

18-57

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

61

4-61

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

43

≤12.1-43

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

12

1-12

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

7.0

1.0-7.0

Only supported for [`SVGPathElement`](https://developer.mozilla.org/docs/Web/API/SVGPathElement), not all `SVGGeometryElement` objects.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGGeometryElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGGeometryElement</a>

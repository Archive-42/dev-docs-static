SVGGraphicsElement
==================

The `SVGGraphicsElement` interface represents SVG elements whose primary purpose is to directly render graphics into a group.

**Note:** This interface was introduced in SVG 2 and replaces the <span class="page-not-created">`SVGLocatable`</span> and [`SVGTransformable`](svgtransformable) interfaces from SVG 1.1.

Properties
----------

*This interface also inherits properties from its parent, [`SVGElement`](svgelement).*

 <span class="page-not-created">`SVGGraphicsElement.transform`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedTransformList`](svganimatedtransformlist) reflecting the computed value of the [`transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) property and its corresponding `transform` attribute of the given element.

Methods
-------

*This interface also inherits methods from its parent, [`SVGElement`](svgelement).*

[`SVGGraphicsElement.getBBox()`](svggraphicselement/getbbox)  
Returns a [`DOMRect`](domrect) representing the computed bounding box of the current element.

<span class="page-not-created">`SVGGraphicsElement.getCTM()`</span>  
Returns a [`DOMMatrix`](dommatrix) representing the matrix that transforms the current element's coordinate system to its SVG viewport's coordinate system.

<span class="page-not-created">`SVGGraphicsElement.getScreenCTM()`</span>  
Returns a [`DOMMatrix`](dommatrix) representing the matrix that transforms the current element's coordinate system to the coordinate system of the SVG viewport for the SVG document fragment.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the equivalent `on...` handler property defined on [`GlobalEventHandlers`](globaleventhandlers) or [`WindowEventHandlers`](windoweventhandlers).

`copy`  
Fired when the user initiates a copy action through the browser's user interface.

`cut`  
Fired when the user has initiated a "cut" action through the browser's user interface.

`paste`  
Fires when the user has initiated a "paste" action through the browser's user interface.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#InterfaceSVGGraphicsElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGGraphicsElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGGraphicsElement`

30

12

20

No

17

6.1

4.4

30

20

18

7

2.0

`getBBox`

30

15

20

\["The `getBBox()` method returns an empty `DOMRect` when there is no fill ([bug 1019326](https://bugzil.la/1019326)).", "This method doesn't work for `<textPath>` and `<tspan>` elements ([bug 937268](https://bugzil.la/937268))."\]

No

17

6.1

4.4

30

20

\["The `getBBox()` method returns an empty `DOMRect` when there is no fill ([bug 1019326](https://bugzil.la/1019326)).", "This method doesn't work for `<textPath>` and `<tspan>` elements ([bug 937268](https://bugzil.la/937268))."\]

18

7

2.0

`getCTM`

30

15

20

No

17

6.1

4.4

30

20

18

7

2.0

`getScreenCTM`

30

15

20

No

17

6.1

4.4

30

20

18

7

2.0

`transform`

Yes

15

20

No

Yes

6.1

Yes

Yes

20

Yes

7

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement</a>

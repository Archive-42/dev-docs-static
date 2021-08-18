SVGGradientElement
==================

The `SVGGradient` interface is a base interface used by [`SVGLinearGradientElement`](svglineargradientelement) and [`SVGRadialGradientElement`](svgradialgradientelement).

Constants
---------

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_SPREADMETHOD_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_SPREADMETHOD_PAD</code></td><td>1</td><td>Corresponds to value <em>pad</em>.</td></tr><tr class="odd"><td><code>SVG_SPREADMETHOD_REFLECT</code></td><td>2</td><td>Corresponds to value <em>reflect</em>.</td></tr><tr class="even"><td><code>SVG_SPREADMETHOD_REPEAT</code></td><td>3</td><td>Corresponds to value <em>repeat</em>.</td></tr></tbody></table>

Properties
----------

*This interface also inherits properties from its parent, [`SVGElement`](svgelement), and implements those of [`SVGURIReference`](svgurireference).*

 <span class="page-not-created">`SVGGradientElement.gradientUnits`</span> <span class="badge inline readonly">Read only </span>   
Returns an [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `gradientUnits` attribute on the given element. Takes one of the constants defined in [`SVGUnitTypes`](svgunittypes).

 <span class="page-not-created">`SVGGradientElement.gradientTransform`</span> <span class="badge inline readonly">Read only </span>   
Returns an [`SVGAnimatedTransformList`](svganimatedtransformlist) corresponding to attribute `gradientTransform` on the given element.

 <span class="page-not-created">`SVGGradientElement.spreadMethod`</span> <span class="badge inline readonly">Read only </span>   
Returns an [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to attribute `spreadMethod` on the given element. One of the spread method types defined on this interface.

Methods
-------

*This interface does not provide any specific methods, but implements those of its parent, [`SVGElement`](svgelement).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/pservers.html#InterfaceSVGGradientElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGGradientElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Removed inheritance of <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a>, <a href="svgstylable"><code>SVGStylable</code></a>, and <a href="svgunittypes"><code>SVGUnitTypes</code></a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/pservers.html#InterfaceSVGGradientElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGGradientElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGGradientElement`

1

≤18

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

`gradientTransform`

1

12

1.5

9

15

3

1

18

4

14

1

1.0

`gradientUnits`

1

12

1.5

9

15

3

1

18

4

14

1

1.0

`spreadMethod`

1

12

1.5

9

15

3

1

18

4

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGGradientElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGGradientElement</a>

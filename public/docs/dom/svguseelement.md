SVGUseElement
=============

SVG use DOM interface
---------------------

The `SVGUseElement` interface corresponds to the [`<use>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/use) element.

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGGraphicsElement`](svggraphicselement) and implements properties from [`SVGURIReference`](svgurireference).*

 <span class="page-not-created">`SVGUseElement.x`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `x` attribute of the given element.

 <span class="page-not-created">`SVGUseElement.y`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `y` attribute of the given element.

 <span class="page-not-created">`SVGUseElement.width`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `width` attribute of the given element.

 <span class="page-not-created">`SVGUseElement.height`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the `height` attribute of the given element.

 <span class="page-not-created">`SVGUseElement.instanceRoot`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGElement`](svgelement) corresponding to the instance root of the given element, which is a direct child of the elements shadow root. If the element does not have a shadow tree (for example, because its URI is invalid or because it has been disabled by conditional processing), then getting this attribute returns `null`.

 <span class="page-not-created">`SVGUseElement.animatedInstanceRoot`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGElement`](svgelement) corresponding to the instance root of the given element, which is a direct child of the elements shadow root. If the element does not have a shadow tree (for example, because its URI is invalid or because it has been disabled by conditional processing), then getting this attribute returns `null`.

Methods
-------

*This interface doesn't implement any specific methods, but inherits methods from its parent interface, [`SVGGraphicsElement`](svggraphicselement) and implements methods from [`SVGURIReference`](svgurireference).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/struct.html#InterfaceSVGUseElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGUseElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Redefined the properties <code>instanceRoot</code> and <code>animatedInstanceRoot</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/struct.html#InterfaceSVGUseElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGUseElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGUseElement`

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

`animatedInstanceRoot`

1-36

12-79

No

9

≤12.1-23

3-9

1-37

18-36

No

≤12.1-24

1-9

1.0-3.0

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

`instanceRoot`

1-37

12-79

No

9

≤12.1-24

3-9

1-37

18-37

No

≤12.1-24

1-9

1.0-3.0

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

-   [`<use>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/use)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGUseElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGUseElement</a>

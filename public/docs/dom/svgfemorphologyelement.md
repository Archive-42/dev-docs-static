SVGFEMorphologyElement
======================

The `SVGFEMorphologyElement` interface corresponds to the [`<feMorphology>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feMorphology) element.

Constants
---------

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_MORPHOLOGY_OPERATOR_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_MORPHOLOGY_OPERATOR_ERODE</code></td><td>1</td><td>Corresponds to the <code>erode</code> value.</td></tr><tr class="odd"><td><code>SVG_MORPHOLOGY_OPERATOR_DILATE</code></td><td>2</td><td>Corresponds to <code>dilate</code> value.</td></tr></tbody></table>

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGElement`](svgelement), and also implements properties of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

 <span class="page-not-created">`SVGFEMorphologyElement.in1`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedString`](svganimatedstring) corresponding to the `in` attribute of the given element.

 <span class="page-not-created">`SVGFEMorphologyElement.operator`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `operator` attribute of the given element. It takes one of the `SVG_MORPHOLOGY_OPERATOR_*` constants defined on this interface.

 <span class="page-not-created">`SVGFEMorphologyElement.radiusX`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the X component of the `radius` attribute of the given element.

 <span class="page-not-created">`SVGFEMorphologyElement.radiusY`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the Y component of the `radius` attribute of the given element.

Methods
-------

*This interface does not provide any specific methods, but implements those of its parent, [`SVGElement`](svgelement), and also implements methods of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#InterfaceSVGFEMorphologyElement">Filter Effects Module Level 1<br />
<span class="small">The definition of 'SVGFEMorphologyElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/filters.html#InterfaceSVGFEMorphologyElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGFEMorphologyElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGFEMorphologyElement`

5

12

3

10

≤12.1

6

≤37

18

4

≤12.1

6

1.0

`in1`

5

12

3

10

15

6

≤37

18

4

14

6

1.0

`operator`

5

12

3

10

15

6

≤37

18

4

14

6

1.0

`radiusX`

5

12

3

10

15

6

≤37

18

4

14

6

1.0

`radiusY`

5

12

3

10

15

6

≤37

18

4

14

6

1.0

See also
--------

-   [`<feMorphology>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feMorphology)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGFEMorphologyElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGFEMorphologyElement</a>

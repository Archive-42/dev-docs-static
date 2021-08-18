SVGFEConvolveMatrixElement
==========================

The `SVGFEConvolveMatrixElement` interface corresponds to the [`<feConvolveMatrix>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feConvolveMatrix) element.

Constants
---------

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_EDGEMODE_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_EDGEMODE_DUPLICATE</code></td><td>1</td><td>Corresponds to the <code>duplicate</code> value.</td></tr><tr class="odd"><td><code>SVG_EDGEMODE_WRAP</code></td><td>2</td><td>Corresponds to the <code>wrap</code> value.</td></tr><tr class="even"><td><code>SVG_EDGEMODE_NONE</code></td><td>3</td><td>Corresponds to <code>none</code> value.</td></tr></tbody></table>

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGElement`](svgelement), and also implements properties of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

 <span class="page-not-created">`SVGFEConvolveMatrixElement.in1`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedString`](svganimatedstring) corresponding to the `in` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.orderX`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedInteger`](svganimatedinteger) corresponding to the `order` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.orderY`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedInteger`](svganimatedinteger) corresponding to the `order` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.kernelMatrix`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumberList`](svganimatednumberlist) corresponding to the `kernelMatrix` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.divisor`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `divisor` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.bias`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `bias` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.targetX`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedInteger`](svganimatedinteger) corresponding to the `targetX` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.targetY`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedInteger`](svganimatedinteger) corresponding to the `targetY` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.edgeMode`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `edgeMode` attribute of the given element. Takes one of the `SVG_EDGEMODE_*` constants defined on this interface.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.kernelUnitLengthX`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `kernelUnitLength` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.kernelUnitLengthY`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `kernelUnitLength` attribute of the given element.

 <span class="page-not-created">`SVGFEConvolveMatrixElement.preserveAlpha`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedBoolean`](svganimatedboolean) corresponding to the `preserveAlpha` attribute of the given element.

Methods
-------

*This interface does not provide any specific methods, but implements those of its parent, [`SVGElement`](svgelement), and also implements methods of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#InterfaceSVGFEConvolveMatrixElement">Filter Effects Module Level 1<br />
<span class="small">The definition of 'SVGFEConvolveMatrixElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/filters.html#InterfaceSVGFEConvolveMatrixElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGFEConvolveMatrixElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGFEConvolveMatrixElement`

6

12

3

10

≤12.1

6

1

18

4

≤12.1

6

1.0

`bias`

6

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

`divisor`

6

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

`edgeMode`

6

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

`in1`

6

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

`kernelMatrix`

6

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

`kernelUnitLengthX`

6

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

`kernelUnitLengthY`

6

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

`orderX`

6

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

`orderY`

6

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

`preserveAlpha`

6

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

`targetX`

6

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

`targetY`

6

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

-   [`<feConvolveMatrix>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feConvolveMatrix)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGFEConvolveMatrixElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGFEConvolveMatrixElement</a>

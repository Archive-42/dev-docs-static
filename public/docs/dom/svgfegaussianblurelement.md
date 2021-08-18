SVGFEGaussianBlurElement
========================

The `SVGFEGaussianBlurElement` interface corresponds to the [`<feGaussianBlur>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feGaussianBlur) element.

Constants
---------

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_EDGEMODE_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_EDGEMODE_DUPLICATE</code></td><td>1</td><td>Corresponds to the <code>duplicate</code> value.</td></tr><tr class="odd"><td><code>SVG_EDGEMODE_WRAP</code></td><td>2</td><td>Corresponds to the <code>wrap</code> value.</td></tr><tr class="even"><td><code>SVG_EDGEMODE_NONE</code></td><td>3</td><td>Corresponds to <code>none</code> value.</td></tr></tbody></table>

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGElement`](svgelement), and also implements properties of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

 <span class="page-not-created">`SVGFEGaussianBlurElement.in1`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedString`](svganimatedstring) corresponding to the `in` attribute of the given element.

 <span class="page-not-created">`SVGFEGaussianBlurElement.stdDeviationX`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the (possibly automatically computed) X component of the `stdDeviation` attribute of the given element.

 <span class="page-not-created">`SVGFEGaussianBlurElement.stdDeviationY`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the (possibly automatically computed) Y component of the `stdDeviation` attribute of the given element.

 <span class="page-not-created">`SVGFEGaussianBlurElement.edgeMode`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `edgeMode` attribute of the given element. Takes one of the `SVG_EDGEMODE_*` constants defined on this interface.

Methods
-------

*This interface also inherits methods of its parent, [`SVGElement`](svgelement), and also implements methods of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

<span class="page-not-created">`SVGFEGaussianBlurElement.setStdDeviation()`</span>  
Sets the values for the `stdDeviation` attribute.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#InterfaceSVGFEGaussianBlurElement">Filter Effects Module Level 1<br />
<span class="small">The definition of 'SVGFEGaussianBlurElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added <code>edgeMode</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/filters.html#InterfaceSVGFEGaussianBlurElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGFEGaussianBlurElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGFEGaussianBlurElement`

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

`edgeMode`

No

No

No

No

No

6.1

No

No

No

No

7

No

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

`setStdDeviation`

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

`stdDeviationX`

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

`stdDeviationY`

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

-   [`<feGaussianBlur>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feGaussianBlur)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGFEGaussianBlurElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGFEGaussianBlurElement</a>

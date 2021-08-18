SVGFETurbulenceElement
======================

The `SVGFETurbulenceElement` interface corresponds to the [`<feTurbulence>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feTurbulence) element.

Constants
---------

### Turbulence types

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_TURBULENCE_TYPE_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_TURBULENCE_TYPE_FRACTALNOISE</code></td><td>1</td><td>Corresponds to the <code>fractalNoise</code> value.</td></tr><tr class="odd"><td><code>SVG_TURBULENCE_TYPE_TURBULENCE</code></td><td>2</td><td>Corresponds to <code>turbulence</code> value.</td></tr></tbody></table>

### Stitch options

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_STITCHTYPE_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_STITCHTYPE_STITCH</code></td><td>1</td><td>Corresponds to the <code>stitch</code> value.</td></tr><tr class="odd"><td><code>SVG_STITCHTYPE_NOSTITCH</code></td><td>2</td><td>Corresponds to <code>noStitch</code> value.</td></tr></tbody></table>

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGElement`](svgelement), and also implements properties of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

 <span class="page-not-created">`SVGFETurbulenceElement.baseFrequencyX`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the X component of the `baseFrequency` attribute of the given element.

 <span class="page-not-created">`SVGFETurbulenceElement.baseFrequencyY`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the Y component of the `baseFrequency` attribute of the given element.

 <span class="page-not-created">`SVGFETurbulenceElement.numOctaves`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedInteger`](svganimatedinteger) corresponding to the `numOctaves` attribute of the given element.

 <span class="page-not-created">`SVGFETurbulenceElement.seed`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `seed` attribute of the given element.

 <span class="page-not-created">`SVGFETurbulenceElement.stitchTiles`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `stitchTiles` attribute of the given element. It takes one of the `SVG_STITCHTYPE_*` constants defined on this interface.

 <span class="page-not-created">`SVGFETurbulenceElement.type`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `type` attribute of the given element. It takes one of the `SVG_TURBULENCE_TYPE_*` constants defined on this interface.

Methods
-------

*This interface does not provide any specific methods, but implements those of its parent, [`SVGElement`](svgelement), and also implements methods of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#InterfaceSVGFETurbulenceElement">Filter Effects Module Level 1<br />
<span class="small">The definition of 'SVGFETurbulenceElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/filters.html#InterfaceSVGFETurbulenceElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGFETurbulenceElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGFETurbulenceElement`

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

`baseFrequencyX`

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

`baseFrequencyY`

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

`numOctaves`

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

`seed`

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

`stitchTiles`

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

`type`

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

-   [`<feTurbulence>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feTurbulence)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGFETurbulenceElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGFETurbulenceElement</a>

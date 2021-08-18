SVGFEBlendElement
=================

The `SVGFEBlendElement` interface corresponds to the [`<feBlend>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feBlend) element.

Constants
---------

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_FEBLEND_MODE_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_FEBLEND_MODE_NORMAL</code></td><td>1</td><td>Corresponds to the value <code>normal</code>.</td></tr><tr class="odd"><td><code>SVG_FEBLEND_MODE_MULTIPLY</code></td><td>2</td><td>Corresponds to the value <code>multiply</code>.</td></tr><tr class="even"><td><code>SVG_FEBLEND_MODE_SCREEN</code></td><td>3</td><td>Corresponds to the value <code>screen</code>.</td></tr><tr class="odd"><td><code>SVG_FEBLEND_MODE_DARKEN</code></td><td>4</td><td>Corresponds to the value <code>darken</code>.</td></tr><tr class="even"><td><code>SVG_FEBLEND_MODE_LIGHTEN</code></td><td>5</td><td>Corresponds to the value <code>lighten</code>.</td></tr></tbody></table>

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGElement`](svgelement), and implements properties of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

 <span class="page-not-created">`SVGFEBlendElement.in1`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedString`](svganimatedstring) corresponding to the `in` attribute of the given element.

 <span class="page-not-created">`SVGFEBlendElement.in2`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedString`](svganimatedstring) corresponding to the `in2` attribute of the given element.

 <span class="page-not-created">`SVGFEBlendElement.mode`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `mode` attribute of the given element. It takes one of the `SVG_FEBLEND_MODE_*` constants defined on this interface.

Methods
-------

*This interface does not provide any specific methods, but implements those of its parent, [`SVGElement`](svgelement), and implements methods of [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#InterfaceSVGFEBlendElement">Filter Effects Module Level 1<br />
<span class="small">The definition of 'SVGFEBlendElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/filters.html#InterfaceSVGFEBlendElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGFEBlendElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGFEBlendElement`

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

`in2`

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

`mode`

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

-   [`<feBlend>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feBlend)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGFEBlendElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGFEBlendElement</a>

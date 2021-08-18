SVGTextPathElement
==================

The `SVGTextPathElement` interface corresponds to the [`<textPath>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/textPath) element.

Constants
---------

### Method types

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TEXTPATH_METHODTYPE_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>TEXTPATH_METHODTYPE_ALIGN</code></td><td>1</td><td>Corresponds to the value <code>align</code>.</td></tr><tr class="odd"><td><code>TEXTPATH_METHODTYPE_STRETCH</code></td><td>2</td><td>Corresponds to the value <code>stretch</code>.</td></tr></tbody></table>

### Spacing types

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TEXTPATH_SPACINGTYPE_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>TEXTPATH_SPACINGTYPE_AUTO</code></td><td>1</td><td>Corresponds to the value <code>auto</code>.</td></tr><tr class="odd"><td><code>TEXTPATH_SPACINGTYPE_EXACT</code></td><td>2</td><td>Corresponds to the value <code>exact</code>.</td></tr></tbody></table>

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGTextContentElement`](svgtextcontentelement), and also implements properties of [`SVGURIReference`](svgurireference).*

 <span class="page-not-created">`SVGTextPathElement.startOffset`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) corresponding to the X component of the `startOffset` attribute of the given element.

 <span class="page-not-created">`SVGTextPathElement.method`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `method` attribute of the given element. It takes one of the `TEXTPATH_METHODTYPE_*` constants defined on this interface.

 <span class="page-not-created">`SVGTextPathElement.spacing`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `spacing` attribute of the given element. It takes one of the `TEXTPATH_SPACINGTYPE_*` constants defined on this interface.

Methods
-------

*This interface does not provide any specific methods, but implements those of its parent, [`SVGTextContentElement`](svgtextcontentelement), and also implements methods of [`SVGURIReference`](svgurireference).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/text.html#InterfaceSVGTextPathElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGTextPathElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/text.html#InterfaceSVGTextPathElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGTextPathElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGTextPathElement`

1

12

2

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`method`

1

12

20

9

≤12.1

3.1

1

18

20

≤12.1

2

1.0

`spacing`

1

12

20

9

≤12.1

3.1

1

18

20

≤12.1

2

1.0

`startOffset`

1

12

20

9

≤12.1

3.1

1

18

20

≤12.1

2

1.0

See also
--------

-   [`<textPath>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/textPath)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGTextPathElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGTextPathElement</a>

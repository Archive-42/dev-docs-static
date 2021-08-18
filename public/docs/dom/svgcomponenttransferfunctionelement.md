SVGComponentTransferFunctionElement
===================================

The `SVGComponentTransferFunctionElement` interface defines a base interface used by the component transfer function interfaces.

Constants
---------

<table><thead><tr class="header"><th>Name</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>SVG_FECOMPONENTTRANSFER_TYPE_UNKNOWN</code></td><td>0</td><td>The type is not one of predefined types. It is invalid to attempt to define a new value of this type or to attempt to switch an existing value to this type.</td></tr><tr class="even"><td><code>SVG_FECOMPONENTTRANSFER_TYPE_IDENTITY</code></td><td>1</td><td>Corresponds to the value <code>identity</code>.</td></tr><tr class="odd"><td><code>SVG_FECOMPONENTTRANSFER_TYPE_TABLE</code></td><td>2</td><td>Corresponds to the value <code>table</code>.</td></tr><tr class="even"><td><code>SVG_FECOMPONENTTRANSFER_TYPE_DISCRETE</code></td><td>3</td><td>Corresponds to the value <code>discrete</code>.</td></tr><tr class="odd"><td><code>SVG_FECOMPONENTTRANSFER_TYPE_LINEAR</code></td><td>4</td><td>Corresponds to the value <code>linear</code>.</td></tr><tr class="even"><td><code>SVG_FECOMPONENTTRANSFER_TYPE_GAMMA</code></td><td>5</td><td>Corresponds to the value <code>gamma</code>.</td></tr></tbody></table>

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGElement`](svgelement).*

 <span class="page-not-created">`SVGComponentTransferFunctionElement.type`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) corresponding to the `type` attribute of the given element. It takes one of the `SVG_FECOMPONENTTRANSFER_TYPE_*` constants defined on this interface.

 <span class="page-not-created">`SVGComponentTransferFunctionElement.tableValues`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumberList`](svganimatednumberlist) corresponding to the `tableValues` attribute of the given element.

 <span class="page-not-created">`SVGComponentTransferFunctionElement.slope`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `slope` attribute of the given element.

 <span class="page-not-created">`SVGComponentTransferFunctionElement.intercept`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `intercept` attribute of the given element.

 <span class="page-not-created">`SVGComponentTransferFunctionElement.amplitude`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `amplitude` attribute of the given element.

 <span class="page-not-created">`SVGComponentTransferFunctionElement.exponent`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `exponent` attribute of the given element.

 <span class="page-not-created">`SVGComponentTransferFunctionElement.offset`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedNumber`](svganimatednumber) corresponding to the `offset` attribute of the given element.

Methods
-------

*This interface does not provide any specific methods, but implements those of its parent, [`SVGElement`](svgelement).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#InterfaceSVGComponentTransferFunctionElement">Filter Effects Module Level 1<br />
<span class="small">The definition of 'SVGComponentTransferFunctionElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No change</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/filters.html#InterfaceSVGComponentTransferFunctionElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGComponentTransferFunctionElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGComponentTransferFunctionElement`

5

≤18

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

`amplitude`

5

12

21

10

15

6

≤37

18

21

14

6

1.0

`exponent`

5

12

21

10

15

6

≤37

18

21

14

6

1.0

`intercept`

5

12

21

10

15

6

≤37

18

21

14

6

1.0

`offset`

5

12

21

10

15

6

≤37

18

21

14

6

1.0

`slope`

5

12

21

10

15

6

≤37

18

21

14

6

1.0

`tableValues`

5

12

21

10

15

6

≤37

18

21

14

6

1.0

`type`

5

12

21

10

15

6

≤37

18

21

14

6

1.0

See also
--------

-   [`SVGFEFuncAElement`](svgfefuncaelement)
-   [`SVGFEFuncBElement`](svgfefuncbelement)
-   [`SVGFEFuncGElement`](svgfefuncgelement)
-   [`SVGFEFuncRElement`](svgfefuncrelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGComponentTransferFunctionElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGComponentTransferFunctionElement</a>

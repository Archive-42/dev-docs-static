SVGFilterElement
================

The `SVGFilterElement` interface provides access to the properties of [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) elements, as well as methods to manipulate them.

Properties
----------

 <span class="page-not-created">`SVGFilterElement.filterUnits`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) that corresponds to the `filterUnits` attribute of the given [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) element. Takes one of the constants defined in [`SVGUnitTypes`](svgunittypes).

 <span class="page-not-created">`SVGFilterElement.primitiveUnits`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedEnumeration`](svganimatedenumeration) that corresponds to the `primitiveUnits` attribute of the given [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) element. Takes one of the constants defined in [`SVGUnitTypes`](svgunittypes).

 <span class="page-not-created">`SVGFilterElement.x`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) that corresponds to the `x` attribute on the given [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) element.

 <span class="page-not-created">`SVGFilterElement.y`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) that corresponds to the `y` attribute of the given [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) element.

 <span class="page-not-created">`SVGFilterElement.width`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) that corresponds to the `width` attribute of the given [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) element.

 <span class="page-not-created">`SVGFilterElement.height`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedLength`](svganimatedlength) that corresponds to the `height` attribute of the given [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) element.

 <span class="page-not-created">`SVGFilterElement.filterResX`</span> <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An [`SVGAnimatedInteger`](svganimatedinteger) that contains the X component of the `filterRes` attribute of the given [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) element.

 <span class="page-not-created">`SVGFilterElement.filterResY`</span> <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An [`SVGAnimatedInteger`](svganimatedinteger) that contains the Y component of the `filterRes` attribute of the given [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter) element.

Methods
-------

 <span class="page-not-created">`SVGFilterElement.setFilterRes()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Sets the values of the `filterRes` attribute.

Specifications
--------------

<table><tbody><tr class="odd"><td>Specification</td><td>Status</td><td>Comment</td></tr><tr class="even"><td><a href="https://drafts.fxtf.org/filter-effects/#InterfaceSVGFilterElement">Filter Effects Module Level 1<br />
<span class="small">The definition of 'SVGFilterElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Removed the inheritance from <span class="page-not-created"><code>SVGLangSpace</code></span>, <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a>, <a href="svgstylable"><code>SVGStylable</code></a>, and <a href="svgunittypes"><code>SVGUnitTypes</code></a> and removed the <code>setFilterRes()</code> function</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/SVG11/filters.html#InterfaceSVGFilterElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGFilterElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGFilterElement`

5

≤18

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

`filterUnits`

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

`height`

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

`href`

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

`primitiveUnits`

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

`width`

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

`x`

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

`y`

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

-   [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGFilterElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGFilterElement</a>

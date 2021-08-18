SVGViewElement
==============

The `SVGViewElement` interface provides access to the properties of [`<view>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/view) elements, as well as methods to manipulate them.

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGElement`](svgelement).*

 <span class="page-not-created">`SVGViewElement.viewTarget`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An [`SVGStringList`](svgstringlist) corresponding to the `viewTarget` attribute of the given [`<view>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/view) element. A list of [`DOMString`](domstring) values which contain the names listed in the `viewTarget` attribute. Each of the `DOMString` values can be associated with the corresponding element using the [`getElementById()`](document/getelementbyid) method call.

Methods
-------

*This interface doesn't implement any specific methods, but inherits methods from its parent interface, [`SVGElement`](svgelement).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/linking.html#InterfaceSVGViewElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGViewElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Removed a mixin <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/linking.html#InterfaceSVGViewElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGViewElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGViewElement`

1

≤18

15

9

≤12.1

1

1

18

15

≤12.1

1

1.0

`viewTarget`

Yes-56

?

Yes-61

?

Yes-43

?

Yes-56

Yes-56

Yes-61

Yes-43

?

Yes-6.0

See also
--------

-   [`<view>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/view)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGViewElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGViewElement</a>

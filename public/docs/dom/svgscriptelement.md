SVGScriptElement
================

The `SVGScriptElement` interface corresponds to the SVG [`<script>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/script) element.

Properties
----------

 <span class="page-not-created">`SVGScriptElement.type`</span> <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) corresponding to the `type` attribute of the given [`<script>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/script) element. A [`DOMException`](domexception) is raised with the code `NO_MODIFICATION_ALLOWED_ERR` on an attempt to change the value of a read only attribut.

 <span class="page-not-created">`SVGScriptElement.crossOrigin`</span> <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) corresponding to the `crossorigin` attribute of the given [`<script>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/script) element.

Methods
-------

*This interface doesn't implement any specific methods, but inherits methods from its parent interface, [`SVGElement`](svgelement).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/interact.html#InterfaceSVGScriptElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGScriptElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Removed the implemented interface <a href="svgexternalresourcesrequired"><code>SVGExternalResourcesRequired</code></a> and added the <code>crossOrigin</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/script.html#InterfaceSVGScriptElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGScriptElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGScriptElement`

1

≤18

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

`crossOrigin`

No

No

14

No

No

No

No

No

14

No

No

No

`type`

1

12

1.5

9

15

3

1

18

4

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGScriptElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGScriptElement</a>

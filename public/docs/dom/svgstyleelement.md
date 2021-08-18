SVGStyleElement
===============

SVG style interface
-------------------

The `SVGStyleElement` interface corresponds to the SVG [`<style>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/style) element.

Properties
----------

*This interface also inherits properties from its parent interface, [`SVGElement`](svgelement) and implements properties from [`LinkStyle`](linkstyle).*

<span class="page-not-created">`SVGStyleElement.type`</span>  
A [`DOMString`](domstring) corresponding to the `type` attribute of the given element.

SVG 1.1 defined that a [`DOMException`](domexception) is raised with code `NO_MODIFICATION_ALLOWED_ERR` on an attempt to change the value of a read-only attribute. This restriction was removed in SVG 2.

<span class="page-not-created">`SVGStyleElement.media`</span>  
A [`DOMString`](domstring) corresponding to the `media` attribute of the given element.

SVG 1.1 defined that a [`DOMException`](domexception) is raised with code `NO_MODIFICATION_ALLOWED_ERR` on an attempt to change the value of a read-only attribute. This restriction was removed in SVG 2.

<span class="page-not-created">`SVGStyleElement.title`</span>  
A [`DOMString`](domstring) corresponding to the `title` attribute of the given element.

SVG 1.1 defined that a [`DOMException`](domexception) is raised with code `NO_MODIFICATION_ALLOWED_ERR` on an attempt to change the value of a read-only attribute. This restriction was removed in SVG 2.

Methods
-------

*This interface doesn't implement any specific methods, but inherits methods from its parent interface, [`SVGElement`](svgelement) and implements methods from [`LinkStyle`](linkstyle).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/styling.html#InterfaceSVGStyleElement">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGStyleElement' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added inheritance of <a href="linkstyle"><code>LinkStyle</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/styling.html#InterfaceSVGStyleElement">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGStyleElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGStyleElement`

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

`media`

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

`title`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGStyleElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGStyleElement</a>

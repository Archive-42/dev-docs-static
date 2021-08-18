SVGURIReference
===============

The `SVGURIReference` interface is used to reflect the `href` attribute and the deprecated `xlink:href` attribute.

Properties
----------

 <span class="page-not-created">`SVGURIReference.href`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGAnimatedString`](svganimatedstring) that represents the value of the `href` attribute, and, on elements that are defined to support it, the deprecated `xlink:href` attribute. On getting `href`, an [`SVGAnimatedString`](svganimatedstring) object is returned that

-   reflects the `href` attribute, and
-   if the element is defined to support the deprecated `xlink:href` attribute, additionally reflects that deprecated attribute.

Methods
-------

*This interface does not provide any specific methods.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#InterfaceSVGURIReference">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGURIReference' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Replaced the deprecated <code>xlink:href</code> attribute reference by the <code>href</code> attribute and made the prior only be reflected where it's defined to be supported.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGURIReference">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGURIReference' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGURIReference`

?

?

?

?

?

?

?

?

?

?

?

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGURIReference" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGURIReference</a>

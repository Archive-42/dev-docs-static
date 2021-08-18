SVGTests
========

The `SVGTests` interface is used to reflect conditional processing attributes and is mixed into other interfaces for elements that support these attributes.

Properties
----------

 <span class="page-not-created">`SVGTests.requiredFeatures`</span> <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An [`SVGStringList`](svgstringlist) corresponding to the `requiredFeatures` attribute of the given element.

 <span class="page-not-created">`SVGTests.requiredExtensions`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGStringList`](svgstringlist) corresponding to the `requiredExtensions` attribute of the given element.

 <span class="page-not-created">`SVGTests.systemLanguage`</span> <span class="badge inline readonly">Read only </span>   
An [`SVGStringList`](svgstringlist) corresponding to the `systemLanguage` attribute of the given element.

Methods
-------

 <span class="page-not-created">`SVGTests.hasExtension()`</span> <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns `true` if the browser supports the given extension, specified by a URI.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/types.html#InterfaceSVGTests">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'SVGTests' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Removed <code>requiredFeatures</code> property and <code>hasExtension()</code> method.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGTests">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGTests' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGTests`

Yes

12

12

9

?

?

Yes

Yes

?

?

?

Yes

`hasExtension`

Yes-47

Removed because it is not part of the SVG2 spec.

?

?

?

?

?

Yes-47

Removed because it is not part of the SVG2 spec.

Yes-47

Removed because it is not part of the SVG2 spec.

?

?

?

Yes-5.0

Removed because it is not part of the SVG2 spec.

`requiredFeatures`

Yes-59

Removed because it is not part of the SVG2 spec.

?

?

?

?

?

Yes-59

Removed because it is not part of the SVG2 spec.

Yes-59

Removed because it is not part of the SVG2 spec.

?

?

?

Yes-7.0

Removed because it is not part of the SVG2 spec.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGTests" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGTests</a>

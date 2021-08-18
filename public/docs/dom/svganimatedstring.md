SVGAnimatedString
=================

The `SVGAnimatedString` interface represents string attributes which can be animated from each SVG declaration. You need to create SVG attribute before doing anything else, everything should be declared inside this.

Properties
----------

 [`SVGAnimatedString.animVal`](svganimatedstring/animval) <span class="badge inline readonly">Read only </span>   
This is a [`DOMString`](domstring) representing the animation value. <span class="field"><span class="_animVal doc">If the given attribute or property is being animated it contains the current animated value of the attribute or property. If the given attribute or property is not currently being animated, it contains the same value as </span></span>baseVal<span class="field"><span class="_animVal doc">.</span></span>

[`SVGAnimatedString.baseVal`](svganimatedstring/baseval)  
This is a [`DOMString`](domstring) representing the base value. <span class="field"><span class="_baseVal doc">The base value of the given attribute before applying any animations. Setter throws DOMException.</span></span>

Methods
-------

*The `SVGAnimatedString` interface do not provide any specific methods.*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGAnimatedString">Scalable Vector Graphics (SVG) 1.1 (Second Edition)</a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://svgwg.org/svg2-draft/types.html#InterfaceSVGAnimatedString">Scalable Vector Graphics (SVG) 2</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`SVGAnimatedString`

5

12

1.5

No

15

5

≤37

18

4

14

4

1.0

`animVal`

Yes

12

1.5

No

Yes

Yes

Yes

No

4

Yes

Yes

No

`baseVal`

Yes

12

1.5

No

Yes

Yes

Yes

No

4

Yes

Yes

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedString</a>

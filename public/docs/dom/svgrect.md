SVGRect
=======

The `SVGRect` represents a rectangle. Rectangles consist of an `x` and `y` coordinate pair identifying a minimum `x` value, a minimum `y` value, and a `width` and `height`, which are constrained to be non-negative.

An `SVGRect` object can be designated as read only, which means that attempts to modify the object will result in an exception being thrown.

Properties
----------

<span class="page-not-created">`SVGRect.x`</span>  
The exact effect of this coordinate depends on each element. If the attribute is not specified, the effect is as if a value of `0` were specified.

<span class="page-not-created">`SVGRect.y`</span>  
The exact effect of this coordinate depends on each element. If the attribute is not specified, the effect is as if a value of `0` were specified.

<span class="page-not-created">`SVGRect.width`</span>  
This represents the width of the rectangle. A value that is negative results to an error. A value of `0` disables rendering of the element

`SVGRect.height`  
This represents the height of the rectangle. A value that is negative results to an error. A value of `0` disables rendering of the element.

Methods
-------

*This interface also inherits properties from its parent, [`DOMRectReadOnly`](domrectreadonly).*

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/geometry/#DOMRect">Geometry Interfaces Module Level 1<br />
<span class="small">The definition of 'DOMRect' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Changed SVGRect as a legacy alias of DOMRect.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGRect">Scalable Vector Graphics (SVG) 1.1 (Second Edition)<br />
<span class="small">The definition of 'SVGRect' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`SVGRect`

1

12

1.5

9

8

3.1

1

18

4

10.1

3.1

1.0

`height`

1

12

1.5

9

?

Yes

1

18

4

?

Yes

1.0

`width`

1

12

1.5

9

?

Yes

1

18

4

?

Yes

1.0

`x`

1

12

1.5

9

?

Yes

1

18

4

?

Yes

1.0

`y`

1

12

1.5

9

?

Yes

1

18

4

?

Yes

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGRect</a>

SVGAnimatedPreserveAspectRatio
==============================

SVG animated preserveAspectRatio interface
------------------------------------------

The `SVGAnimatedPreserveAspectRatio` interface is used for attributes of type [`SVGPreserveAspectRatio`](svgpreserveaspectratio) which can be animated.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><em>None</em></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly float <code>baseVal</code></li><li>readonly float <code>animVal</code></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/coords.html#InterfaceSVGAnimatedPreserveAspectRatio">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

 <span class="page-not-created">`SVGAnimatedPreserveAspectRatio.baseVal`</span> <span class="badge inline readonly">Read only </span>   
Is a [`SVGPreserveAspectRatio`](svgpreserveaspectratio) that represents the base value of the given attribute before applying any animations.

 <span class="page-not-created">`SVGAnimatedPreserveAspectRatio.animVal`</span> <span class="badge inline readonly">Read only </span>   
Is a [`SVGPreserveAspectRatio`](svgpreserveaspectratio) that represents the current animated value of the given attribute. If the given attribute is not currently being animated, then the [`SVGPreserveAspectRatio`](svgpreserveaspectratio) will have the same contents as `baseVal`. The object referenced by `animVal` is always distinct from the one referenced by `baseVal`, even when the attribute is not animated.

Methods
-------

The `SVGAnimatedPreserveAspectRatio` interface do not provide any specific methods.

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

`SVGAnimatedPreserveAspectRatio`

5

12

1.5

9

15

5

≤37

18

4

14

4

1.0

`animVal`

5

12

22

10

15

6

≤37

18

22

14

6

1.0

`baseVal`

5

12

22

10

15

6

≤37

18

22

14

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedPreserveAspectRatio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedPreserveAspectRatio</a>

SVGAnimatedNumberList
=====================

SVG animated number list interface
----------------------------------

The `SVGAnimatedNumber` interface is used for attributes which take a list of numbers and which can be animated.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><em>None</em></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly <a href="svgnumberlist"><code>SVGNumberList</code></a> <code>baseVal</code></li><li>readonly <a href="svgnumberlist"><code>SVGNumberList</code></a> <code>animVal</code></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGAnimatedAngle">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

 <span class="page-not-created">`SVGAnimatedNumberList.baseVal`</span> <span class="badge inline readonly">Read only </span>   
Is a [`SVGNumberList`](svgnumberlist) that represents the base value of the given attribute before applying any animations.

 <span class="page-not-created">`SVGAnimatedNumberList.animVal`</span> <span class="badge inline readonly">Read only </span>   
Is a read only [`SVGNumberList`](svgnumberlist) that represents the current animated value of the given attribute. If the given attribute is not currently being animated, then the [`SVGNumberList`](svgnumberlist) will have the same contents as `baseVal`. The object referenced by `animVal` will always be distinct from the one referenced by `baseVal`, even when the attribute is not animated.

Methods
-------

The `SVGAnimatedNumberList` interface do not provide any specific methods.

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

`SVGAnimatedNumberList`

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

6

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

`baseVal`

6

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedNumberList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedNumberList</a>

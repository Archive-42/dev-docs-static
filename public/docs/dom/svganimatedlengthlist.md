SVGAnimatedLengthList
=====================

SVG animated length list interface
----------------------------------

The `SVGAnimatedLengthList` interface is used for attributes of type [`SVGLengthList`](svglengthlist) which can be animated.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><em>None</em></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly <a href="svglengthlist"><code>SVGLengthList</code></a> <code>baseVal</code></li><li>readonly <a href="svglengthlist"><code>SVGLengthList</code></a> <code>animVal</code></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGAnimatedLengthList">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

<table><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>baseVal</code></td><td><a href="svglengthlist"><code>SVGLengthList</code></a></td><td>The base value of the given attribute before applying any animations.</td></tr><tr class="even"><td><code>animVal</code></td><td><a href="svglengthlist"><code>SVGLengthList</code></a></td><td>A read only <a href="svglengthlist"><code>SVGLengthList</code></a> representing the current animated value of the given attribute. If the given attribute is not currently being animated, then the <a href="svglengthlist"><code>SVGLengthList</code></a> will have the same contents as <code>baseVal</code>. The object referenced by <code>animVal</code> will always be distinct from the one referenced by <code>baseVal</code>, even when the attribute is not animated.</td></tr></tbody></table>

Methods
-------

The `SVGAnimatedLengthList` interface do not provide any specific methods.

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

`SVGAnimatedLengthList`

1

12

1.5

9

15

3

???37

18

4

14

1

1.0

`animVal`

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

`baseVal`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedLengthList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedLengthList</a>

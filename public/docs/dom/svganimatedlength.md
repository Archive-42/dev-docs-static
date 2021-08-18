SVGAnimatedLength
=================

SVG animated length interface
-----------------------------

The `SVGAnimatedLength` interface is used for attributes of basic type [&lt;length&gt;](https://developer.mozilla.org/en-US/docs/Web/SVG/Content_type#length) which can be animated.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><em>None</em></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly <a href="svglength"><code>SVGLength</code></a> <code>baseVal</code></li><li>readonly <a href="svglength"><code>SVGLength</code></a> <code>animVal</code></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGAnimatedLength">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

<table><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>baseVal</code></td><td><a href="svglength"><code>SVGLength</code></a></td><td>The base value of the given attribute before applying any animations.</td></tr><tr class="even"><td><code>animVal</code></td><td><a href="svglength"><code>SVGLength</code></a></td><td>If the given attribute or property is being animated, contains the current animated value of the attribute or property. If the given attribute or property is not currently being animated, contains the same value as <code>baseVal</code>.</td></tr></tbody></table>

Methods
-------

The `SVGAnimatedLength` interface do not provide any specific methods.

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

`SVGAnimatedLength`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedLength" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedLength</a>

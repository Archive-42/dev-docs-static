SVGAnimatedNumber
=================

SVG animated number interface
-----------------------------

The `SVGAnimatedNumber` interface is used for attributes of basic type [&lt;Number&gt;](https://developer.mozilla.org/en-US/docs/Web/SVG/Content_type#number) which can be animated.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><em>None</em></td></tr><tr class="odd"><td>Properties</td><td><ul><li>float <code>baseVal</code></li><li>readonly float <code>animVal</code></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/types.html#InterfaceSVGAnimatedNumber">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

<table><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>baseVal</code></td><td>float</td><td>The base value of the given attribute before applying any animations.</td></tr><tr class="even"><td><code>animVal</code></td><td>float</td><td>If the given attribute or property is being animated, contains the current animated value of the attribute or property. If the given attribute or property is not currently being animated, contains the same value as <code>baseVal</code>.</td></tr></tbody></table>

Methods
-------

The `SVGAnimatedNumber` interface do not provide any specific methods.

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

`SVGAnimatedNumber`

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

79

1.5

No

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

79

1.5

No

15

3

1

18

4

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedNumber" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedNumber</a>

SVGAnimatedPoints
=================

SVG animated points interface
-----------------------------

The `SVGAnimatedPoints` interface supports elements which have a `points` attribute which holds a list of coordinate values and which support the ability to animate that attribute.

Additionally, the `points` attribute on the original element accessed via the XML DOM (e.g., using the `getAttribute()` method call) will reflect any changes made to the `SVGAnimatedPoints.points` attribut.

### Interface overview

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td>Also implement</td><td><em>None</em></td></tr><tr class="even"><td>Methods</td><td><em>None</em></td></tr><tr class="odd"><td>Properties</td><td><ul><li>readonly <span class="page-not-created"><code>SVGPointList</code></span> <code>points</code></li><li>readonly <span class="page-not-created"><code>SVGPointList</code></span> <code>animatedPoints</code></li></ul></td></tr><tr class="even"><td>Normative document</td><td><a href="https://www.w3.org/TR/SVG11/shapes.html#InterfaceSVGAnimatedPoints">SVG 1.1 (2nd Edition)</a></td></tr></tbody></table>

Properties
----------

<table><thead><tr class="header"><th>Name</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>points</code></td><td><span class="page-not-created"><code>SVGPointList</code></span></td><td>Provides access to the base (i.e., static) contents of the <code>points</code> attribute.</td></tr><tr class="even"><td><code>animatedPoints</code></td><td><span class="page-not-created"><code>SVGPointList</code></span></td><td>Provides access to the current animated contents of the <code>points</code> attribute. If the given attribute or property is being animated, contains the current animated value of the attribute or property. If the given attribute or property is not currently being animated, contains the same value as <code>points</code>.</td></tr></tbody></table>

Methods
-------

The `SVGAnimatedPoints` interface do not provide any specific methods.

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

`SVGAnimatedPoints`

1

12

1.5-21

9

15

1

1

18

4-21

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedPoints" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimatedPoints</a>
